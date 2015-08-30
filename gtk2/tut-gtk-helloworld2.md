## 升级版的 Hello World

现在，我们一起来看看一个升级版的 helloworld，它包含了更多代码块的和控件包装，这也是我们下一个阶段的主题。

	#!/usr/bin/env ruby
	
	# Initializes Ruby/GTK2, as usual.
	require 'gtk2'
	
	# A push on a button will call this method.
	def callback(widget)
	  # Display the 'label' property of the widget.
	  # Refer to the API reference for more information.
	  puts "Hello again - #{widget.label}(#{widget}) was pressed."
	end
	
	# Creates the window.
	window = Gtk::Window.new
	
	# Specify the title and border of the window.
	window.title = "Hello Buttons"
	window.border_width = 10
	
	# The program will directly end upon 'delete_event'.
	window.signal_connect('delete_event') do
	  Gtk.main_quit
	  false
	end
	
	# We create a box to pack widgets into.  
	# This is described in detail in the following section.
	# The box is not really visible, it is just used as a tool to arrange 
	# widgets.
	box1 = Gtk::HBox.new(false, 0)
	
	# Put the box into the main window.
	window.add(box1)
	
	# Creates a new button with the label "Button 1".
	button1 = Gtk::Button.new("Button 1")
	
	# Now when the button is clicked, we call the "callback" method
	# with a reference to "button 1" as its argument.
	button1.signal_connect( "clicked" ) do |w|
	  callback(w)
	end
	
	# Instead of window.add, we pack this button into the invisible
	# box, which has been packed into the window.
	box1.pack_start(button1, true, true, 0)
	
	# Do these same steps again to create a second button.
	button2 = Gtk::Button.new("Button 2")
	
	# Call the same callback function with a different argument,
	# passing a reference to "button 2" instead.
	button2.signal_connect("clicked") do |w|
	  callback(w)
	end
	
	# Pack the second button in a box as well.
	box1.pack_start(button2, true, true, 0)
	
	# You may call the show method of each widgets, as follows:
	#   button1.show
	#   button2.show
	#   box1.show
	#   window.show 
	window.show_all
	Gtk.main

就像第一个 helloworld 一样，你发现没有简单的方式可以退出程序，你只能使用窗口管理器或者命令行来杀掉它。

读者可以尝试添加一个 Quit 按钮来退出程序。

你或许也想在开始下一章之前把玩一下 Gtk::Box#pack_start 的参数，试着改变窗口的大小，然后看看表现。