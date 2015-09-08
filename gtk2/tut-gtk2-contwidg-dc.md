#### 装饰器容器

目前为止每个程序中都会用到 Gtk::Window 类，这是从 Gtk::Bin 派生出来的控件。Bin 类是一个只能包含一个子控件的容器。从这个类派生出来的控件叫做装饰器容器。它们赋予子类一些功能。比如说， Gtk::Window 使它的子控件变成顶层控件，Gtk::Button 则把它的子类变成可点击的实体， Gtk::Frame 给它的子控件周围画一个边框，Gtk::EventBox 则使得它的子类不能自己捕获 GDK 事件，而通过子类来捕获，或者 Gtk::Expander 根据用户需要显示或者隐藏子类。

下面是从 Gtk::Bin 派生出来的类（装饰器）：

+ Gtk::Window
+ Gtk::Alignment
+ Gtk::Frame
+ Gtk::Button
+ Gtk::Item
+ Gtk::ComboBox
+ Gtk::EventBox
+ Gtk::HandleBox
+ Gtk::ToolItem
+ Gtk::ScrolledWindow
+ Gtk::Viewport