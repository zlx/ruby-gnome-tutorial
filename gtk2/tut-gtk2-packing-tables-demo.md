## 表格式包装实例

这里，我们构造了一个包含三个按钮的 2x2 表格。前两个按钮时放在第一行，第三个，退出按钮，放在下一行，占满整行。

下面是源代码:

	#!/usr/bin/env ruby
	
	require 'gtk2'
	
	window = Gtk::Window.new("Table")
	window.signal_connect("delete_event") do
	    Gtk.main_quit
	    false
	end
	window.border_width = 20
	
	# Creates a 2x2 table.
	table = Gtk::Table.new(2, 2, true)
	window.add(table)
	
	[1, 2].each do |i|
	    button = Gtk::Button.new("button #{i}")
	    button.signal_connect("clicked") do
	        puts "Hello again - button #{i} was pressed"
	    end
	    # Insert button 1 into the upper left quadrant of the table,
	    # and button 2 into the upper right quadrant of the table.
	    table.attach_defaults(button, i - 1, i, 0, 1)
	end
	
	button = Gtk::Button.new("Quit")
	button.signal_connect("clicked") do
	    Gtk::main_quit
	end
	
	# Insert the quit button into the both lower quadrants of the table.
	table.attach_defaults(button, 0, 2, 1, 2)
	
	window.show_all
	Gtk.main