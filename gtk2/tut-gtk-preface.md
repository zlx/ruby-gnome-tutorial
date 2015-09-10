## 关于 GTK

(根据 [GTK 教程]())

GTK（GIMP 工具包） 是一个用来创建图形界面的库。它是在LGPL下许可使用的，所以你可以用 GTK 来开发开源软件，免费软件甚至于商业非免费的软件，而不必花任何许可或特许使用费。

它子所以被称为 GIMP 工具包，是因为它最初是用来开发 GNU Image Manipulation Program(GIMP) 的，但是现在 GTK 已经被一大批软件项目使用了，包括 GNU Network Object Model Environment(GNOME) 项目。GTK 是基于 GDK（GIMP 绘画包），一个对操作窗口函数的底层函数的封装，和 gdk-pixbuf ，一个客户端的图片操作库，之上创建的。

GTK 的主要作者是：

+ Peter Mattis
+ Spencer Kimball
+ Josh MacDonald

GTK 现在的主要维护者是：

+ Owen Taylor
+ Tim Janik

GTK 本质上说是一个面向对象的应用程序接口。虽然是用 C 写的，但却是使用了类和函数回调的思想来实现的。

还有一个第三方的组件叫 GLib，它包含了一些标准调用的替换实现，和一些额外的处理函数，比如说列表处理等等。这些替换实现是用来提高 GTK 的移植性的，这里的一些实现并不可用或者并不符合其它 Unix 系统上的标准，比如 g_strerror()。有一些则是对 libc 版本的增强，比如 g_malloc() 添加了调试工具。

在 2.0 版本中， GLib 还引入了构成了 GTK 类层次结构的基础的类型系统，GTK 中已经广泛使用的信号系统，将多个不同平台本地化的线程借口抽象成统一的线程接口和一种加载模块的方式。

最后，GTK 使用 Pango 库来实现国际化文本的输出。

## 关于 Ruby-GNOME2

(根据 [Ruby-GNOME2 教程]())

Ruby 是一种可以快速和简单地进行面向对象编程的解释性脚本语言。它有一种简单的语法来处理错误的异常处理功能。这些操作都是方法的语法糖，你可以很方便的重新定义它们。Ruby 是真正的面向对象语言，它意味着 Ruby 里面任何东西都是对象。Ruby 还是跨平台的，他可以运行在任何 UNIX， DOS， Windows，Mac 等操作系统上。

Ruby 的主要作者时：

+ Yukihiro Matsumoto (Matz)

Ruby-GNOME2 是用 Ruby 语言来调用 GTK 库的一种实现，就像一些 GNOME 库一样。 Ruby-GNOME2 提供了一种方式，可以让你用来写任何 Ruby 可以写的东西的前端窗口。

