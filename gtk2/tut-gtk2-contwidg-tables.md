## 容器控件

这个主题已经被这个教程的原作者 Laurent Sansonetti 在 [用表格打包]() 里面提到过了。然而，因为日版 GTK＋ 教程的翻译工作还未完成，所以我决定使用这个作为我们简短介绍，因此，你会多次看到这段内容。如果你嫌麻烦，可以直接跳到下一个章节 [固定容器]()。

## 表格

到目前为止，除了[用表格包装]()中提到的以外，所有布局容器都允许我们在二维空间内包装。Gtk::Table 比使用多个 Gtk::HBox 和 Gtk::VBox 包装的优势在于相邻的行列中的子控件是自动对齐的。但是有时候，这并不是你希望的，所以盒子就变成了最好的选择。虽然如此，这里我们只专注于 Gtk::Table 类。下面的表和程序中展示了在一个简单表中排列着三个控件：

![contwidg-table-grid-s1](gtk2/contwidg-table-grid-s1.png)

这个例子说明了表格允许一个控件跨域多个行和列提供了钜形布局这个事实。当你阅读下面的程序时，请关注 Gtk::Table#table_attach 这个方法。特别是 left, right, top, bottom 这几个参数的顺序。这些参数定义了表格中独立的单元格。事实上，首先要知道的点是 (0, 0) 表示左上角。其他的点则用 left， right， top， bottom 分别代表(x1, x2） 和 (y1, y2) 来表示表格的坐标 ，当然，我们更熟悉的是基础数学课上学到的表示点的方式,也就是 (x1, y1) 和 (x2, y2)。![contwidg-tables](gtk2/contwidg-tables.png) 为了理解 Gtk::Tables, 你需要转换思维模式。参见上图，每个单元格用 (x1, x2) 和 (y1, y2) 这样的坐标对来标识，而不是我们标准数学坐标的形式 (x, y)。

以下是按照右上角图示一样摆放控件的程序实现。

```ruby
#!/usr/bin/env ruby

require 'gtk2'

window = Gtk::Window.new
window.border_width = 10
window.set_size_request(150, -1)
window.title = "tables"

window.signal_connect('delete_event') { false }
window.signal_connect('destroy') { Gtk.main_quit }

                  # rows, columns, homogeneous
table = Gtk::Table.new(2,    2,    true)

label1 = Gtk::Label.new("Enter the following information ...")
label2 = Gtk::Label.new("Name: ")
name = Gtk::Entry.new

options = Gtk::EXPAND|Gtk::FILL
            # child, x1, x2, y1, y2, x-opt,   y-opt,   xpad, ypad
table.attach(label1,  0,  2,  0,  1, options, options, 0,    0)
table.attach(label2,  0,  1,  1,  2, options, options, 0,    0)
table.attach(name,    1,  2,  1,  2, options, options, 0,    0)

window.add(table)
window.show_all
Gtk.main
```

注意这个坐标系统是从左上角开始的。要把一个控件放到一个单元格中，你可以使用如下方法：

	Gtk::Table#attach(child, 
	                  left_attach, right_attach, top_attach, bottom_attach, 
	                  xoptions, yoptions, 
	                  xpadding, ypadding)
	                  
第一个参数是你想要放进去的控件。几个 attach 参数指明了控件放置的位置，和它所占用的单元格数目。如果你希望把控件放置在右下角的区域，那 left_attach = 1, right_attach = 2, top_attach = 1, bottom_attach = 2。

如果你想让它占满第一行，那就这样设置 left_attach = 0, right_attach = 2, top_attach = 0, bottom_attach = 1。

xoptions, yoptions 则用于指定包装选项的，并且可以把多个选项按位与在一起。

这些选项分别是：

  + Gtk::FILL
  
    如果表格的单元格比控件大，那这个控件就会扩展到整个空间
    
  + Gtk::SHRINK
  
    如果表格的单元格不够放置控件（通常是用户改变了窗口大小），那控件通常会消失，如果指定了 Gtk::SHRINK ，那控件就会和表格一起缩小。
  
  + Gtk::EXPAND  
  
    这会让表格自动占满整个窗口空间
    
就像在 Gtk::Box 中一样， padding 也会在控件周围添加一些额外的空间。

Gtk::Table#attach 有很多参数，所以有一种缩写形式：

    Gtk::Table#attach_defaults(widget, left_attach, right_attach, top_attach, bottom_attach)

默认的 options 是 Gtk::FILL | Gtk::EXPAND，padding 则是 0。剩余的参数则是之前的方法中指定的。

另外，我们还有 Gtk::Table#set_row_spacing 和 Gtk::Table#set_col_spacing 。这是用来制定行或者列之间的间隔的。

	Gtk::Table#set_row_spacing(row, spacing)
	Gtk::Table#set_col_spacing(column, spacing)
	
注意，对于列，间隔是位于列的右边的，而对于行，间隔是位于行之下的。

你可以这样指定所有行或者列的间隔：

	Gtk::Table#set_row_spacings(spacing)
	Gtk::Table#set_col_spacings(spacing)	          
	
注意这些调用都不会在最后一行或者列加上多余的间隔。

### GtkAttachOptions (文档：Gtk模块)

表示当父类改变大小时，一个控件将具有自动扩展属性

+ EXPAND = 1 << 0。表示这个控件将自动扩展直到到占满包含它的容器的可用空间
+ SHRINK = 1 << 1。当需要时，这个控件会收缩。
+ FILL = 1 << 2。这个控件会占满整个可用空间。