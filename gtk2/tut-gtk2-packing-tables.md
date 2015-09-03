## 使用表格包装

我们再来看看另外一种包装形式－－表格。这种形式在某些情况下特别有用。

使用表格，我们就创建了一个可以用来放置控件的网格。这些控件可以按照我们需要占满空间。

首先，当然需要看看 Gtk::Table.new 这个构造器：

    Gtk::Table.new(rows, columns, homogeneous)

第一个参数指定了表格的行数，第二个参数则是指定了表格的列数。homogeneous 参数则用来指定表格单元格如何确定大小。如果 homogeneous 是 true, 表格单元格是按照表格中最大的控件决定的。如果 homogeneous 是 false, 单元格的大小是按照统一行中最高的和同一列中最宽的控件决定的。

行列是从按照从 0 到 n 排列的，n 就是用 Gtk::Table.new 构造时候传递的参数。所以，如果你指定行为 2， 列为 2，那表格的框架就是这样的：

	.0          1          2
	0+----------+----------+
	 |          |          |
	1+----------+----------+
	 |          |          |
	2+----------+----------+

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