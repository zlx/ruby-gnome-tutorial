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

注意坐标系统是从左上角开始的。要把一个控件放到盒子里，用下面这个方法：

```ruby
Gtk::Table#attach(child, 
                  left_attach, right_attach, top_attach, bottom_attach, 
                  xoptions, yoptions, 
                  xpadding, ypadding)
```