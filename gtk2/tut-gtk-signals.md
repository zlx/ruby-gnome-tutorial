## 理解信号和回调机制

在研究 Hello World 的细节之前，我们先来学习一下 GTK 是如何处理信号和回调的。

就像你的操作系统给进程发信号一样（'1）, 当一个特定的事件发生时，GTK 给主循环发送一个信号。主循环就调用控件的对应处理函数。

当信号被接收以后，主循环再次进入睡眠。

为了告诉 GTK 控件去捕获特定的事件，然后执行相应的代码，我们需要设置一个信号处理器。

这就是 GLib::Instantiatable#signal_connect 方法所完成的事情，这是 Ruby/GLib 库的一部分（不要忘了 GTK 是基于 GLib 构建的）。

    GLib::Instantiatable#signal_connect("signal name") do
	    # Code to execute when "signal name" is caught.
	end
	
GLib::Instantiatable#signal_connect 需要两个东西：

+ 需要捕获的信号名字
+ 一段信号产生时候需要执行的代码

这段代码可以像下面一样带一个参数：

    GLib::Instantiatable#signal_connect("signal name") do |w|
	    # ...
	end
	
这个触发信号的控件会被填入参数 w 。

'1 注意 GTK 信号和任何 UNIX 信号无关， GTK 工具是独立于它地下的操作系统的	