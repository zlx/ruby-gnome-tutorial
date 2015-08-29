## 开始

很显然，你需要先把 Ruby-GNOME2 安装到你的机器上。请参照我们的[安装说明]()。如果里面没有你的系统，请从 SourceForge 上面下载最新的包，解压缩然后参考 README 文件以获得进一步的指导。

(最近，安装方式有了很大的改变，请参考[安装文档]())

在开始介绍 GTK 之前，我们先从一个最简单的程序开始。这个例子构造了一个 200x200 的窗口并且只能从 shell 里面杀掉。

    require 'gtk2'
	window = Gtk::Window.new
	window.show
	Gtk.main
	
保存这段程序并命名为 base.rb 然后这样调用:

    ruby base.rb
    
我们接下来逐行讲解一下这段程序。

第一行引入 Ruby/GTK2 这个库。

    require 'gtk2'

第二行用 Gtk::Window.new 创建了一个新的 GTK 窗口，并使用了以下默认参数：

+ 大小: 200x200
+ 样式: Gtk::Window::TOPLEVEL
+ 样式: Gtk::Window::POPUP(***无效***)
+ 标题: 就是你的程序名(这里是 base.rb)

    window = Gtk::Window.new
    
第三行调用了 Gtk::Window#show 来显示我们刚创建的这个窗口

    window.show
    
最后一行进入 GTK 的主循环:

    Gtk.main

你会在任何 Ruby/GTK2 应用程序中看到调用 Gtk.main 。当程序执行到这里时，GTK 会进入睡眠，等待事件触发（比如按钮或者鼠标点击），超时或者文件IO通知等等。当然，在我们这个简单程序中，事件都被忽略了。

#### 关于警告部分

理论上说 GTK 原版C库里面的所有功能都应该在 Ruby 中找到，然后，有一些没有影响或者绝对不需要的，都被省略了。为了保持完整，我在下面警告中指出这些省略的部分和一些相关的不同之处。

### 警告

你之前也看到了，窗口样式可以是 Gtk::Window::TOPLEVEL 或者 Gtk::Window::POPUP。当你需要控制 top-level 样式窗口的大小和位置时，它基本上是由窗口管理器控制的。然后， pop-up 样式的窗口可不一样。它们主要是用于哪些不认为是窗口的东西，比如说工具提示和菜单。窗口管理器会忽略它们，所以它们没有装饰器和边框。在 Ruby 里面，POPUP 类型的窗口大部分时候是忽略掉的，以后，基本上只有一种窗口的样式，那就是默认的 Gtk::Window::TOPLEVEL 。

这就是为什么窗口的实例可以接受窗口样式的参数，能够在文档中找到，但是又不起作用的原因。

另外，不要因为不需要窗口边框就使用 Gtk::Window::POPUP , 这时候使用 Gtk::Window#decorated= 就好了:

	window = Gtk::Window.new(type = Gtk::Window::TOPLEVEL)
	window.decorated = false


        	