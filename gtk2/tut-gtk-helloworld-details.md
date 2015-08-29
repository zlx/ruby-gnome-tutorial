## Ruby/GTK2 的 Hello World（详解）

现在我们已经了解了信号和事件，那我们就来看看 Hello World 程序吧。

首先，初始化 Ruby/GTK2, 这部分是每个 Ruby/GTK2 程序都需要的。

    #!/usr/bin/env ruby
	=begin
	  helloworld.rb - Ruby/GTK first sample script.
	
	  Copyright (c) 2002,2003 Ruby-GNOME2 Project Team
	  This program is licenced under the same licence as Ruby-GNOME2.
	
	  $Id: helloworld.rb,v 1.4 2003/02/01 16:46:22 mutoh Exp $
	=end
	
	require 'gtk2'
	
这里，我们创建了一个叫 Hello World 的按钮。Gtk::Button.new 可以创建了一个按钮，然后根据我们的参数设置它的 label 。现在，这个按钮还不是 GTK 窗口的一部分，并且没有显示。

	button = Gtk::Button.new("Hello World")

下面的代码会在每次按钮点击的时候在控制台打印出 “Hello World” 。

这是通过把一段代码绑定在 clicked 信号上面来实现的。

	button.signal_connect("clicked") {
	  puts "Hello World"
	}

现在，我们该创建窗口了。就像按钮一样，这个窗口还没有显示在屏幕上。

	window = Gtk::Window.new
	
我们把多个信号绑定在这个窗口上：

+ delete_event 会在窗口管理器杀掉这个窗口（通常是用户手动关闭）时触发。注意，我们在这个处理里面返回了 false， 所以这个事件进程还没有结束， GTK 会继续抛出 destroy 信号。
+ destroy 会在 delete_event 之后抛出，这里，我们用 Gtk.main_quit 来退出这个应用程序。

当用户关闭窗口时，会打印出两条消息，首先是 “delete event occured”， 然后是 “destroy event occcured”。

	window.signal_connect("delete_event") {
	  puts "delete event occurred"
	  #true
	  false
	}
	
	window.signal_connect("destroy") {
	  puts "destroy event occurred"
	  Gtk.main_quit
	}

我们把窗口的边框设置为 10 像素， 什么意思？

GTK 窗口其实是一个容器。一个容器其实是一个可以包含其它控件的控件。我们这里的窗口会在它所包含的控件外面显示10像素的边框。

	window.border_width = 10

现在是时候关联我们的按钮和窗口了，我们可以把按钮打包进窗口。

	window.add(button)

下一步是把我们的东西显示出来。我们需要显示两个控件，按钮和窗口，

所以我们可以这样写：

	button.show
	window.show

但是吗，由于按钮已经打包进窗口了，我们可以直接调用窗口的 Gtk::Widget#show_all。这个方法会调用窗口和它包含的控件的 Gtk::Widget#show 方法。

	window.show_all

最后，调用 Gtk.main 进入主循环。程序会进入睡眠，直到 X Window 事件触发，注意，Gtk.main 不会返回。

但是用户依然可以结束应用，因为我们在 destroy 信号触发的时候调用了 Gtk.main_quit 

	Gtk.main
	