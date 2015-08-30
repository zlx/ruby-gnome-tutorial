## 更多关于信号的处理

让我们再看一看 GLib::Instantiatable#signal_connect:

	% irb --simple-prompt
	>> require 'gtk2'
	=> true
	>> b = Gtk::Button.new("hoge")
	=> #<Gtk::Button:0x40a2a858 ptr=0x8237df8>
	>> b.signal_connect("clicked") { puts 1 }
	=> 1
	>> b.signal_connect("clicked") { puts 2 }
	=> 2
	>>

注意到这个返回值了吗？

这是一个用来标识回调的标记。就像之前所说，你可以在一个信号上绑定多个回调，它们会按照绑定的顺序依次执行。

现在，我们来手动出发一个信号。 GLib::Instantiatable#signal_emit 可以用来触发信号。

你可以看到我们的代码块按照它们绑定的顺序触发：

    >> b.signal_emit("clicked")
	1 
	2
	=> nil
	>>

GLib::Instantiatable#signal_handler_disconnect 是用来移除一个已绑定的信号处理的，一个信号处理就是用 GLib::Instantiatable#signal_connect 返回的标识来标记的。

    >> b.signal_handler_disconnect 1
	=> #<Gtk::Button:0x40a2a858 ptr=0x8237df8>
	>> b.signal_emit("clicked")
	2
	=> nil
	>>

你可以用 GLib::Instantiatable#signal_handler_block 和 GLib::Instantiatable#signal_handler_unblock 来临时禁用一个回调代码块。

   >> b.signal_handler_block 2
	=> #<Gtk::Button:0x40a2a858 ptr=0x8237df8>
	>> b.signal_emit("clicked")
	=> nil
	>> b.signal_handler_unblock 2
	=> #<Gtk::Button:0x40a2a858 ptr=0x8237df8>
	>> b.signal_emit("clicked")
	2
	=> nil
	>>    
        
    