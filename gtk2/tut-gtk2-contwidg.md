## 容器控件

### 容器控件的子菜单

+ 容器控件（本页面）
  + 装饰器容器
  + 布局容器
+ 水平和垂直盒子
+ 表格
+ 固定大小容器
+ 扩展器
+ 处理器盒子
+ 记事本
+ 事件盒子

### 简单介绍

我们这里介绍两种容器控件：装饰器和布局容器。然后我们接着介绍上面列表里面提到的其它容器。

### 容器控件

Gtk::Container 类是所有 GTK+ 控件的抽象父类。它包含了所有控件都有的样式和基本行为。Container 类是 Gtk::Widget 类的直接子类，因此，所有 Container 对象都是控件。这是很重要的，因为当你寻找你一个功能是，它可能是由 Widget 类提供的，Widget 提供了大量的方法，属性和信号。然而，我们这里就只关心容器控件。

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

#### 布局控件

+ Gtk::Alighment 一个可以控制子类对齐方式和大小的控件
+ Gtk::AspectFrame 一个可以按照特定比率约束其子类的控件
+ Gtk::HBox 一个水平容器盒子
+ Gtk::VBox 一个垂直容器盒子
+ Gtk::HButtonBox 一个用来水平放置按钮的容器
+ Gtk::VButtonBox 一个用来垂直放置按钮的容器
+ Gtk::Fixed 一个可以让你用绝对坐标固定控件位置的容器
+ Gtk::HPaned 一个包含两个按照水平方式排列的面板的容器
+ Gtk::VPaned 一个包含两个按照垂直方式排列的面板的容器
+ Gtk::Layout 包含子控件和/或者自定义绘画的无限滚动区域
+ Gtk::Notebook 一个标签式的记事本容器
+ Gtk::Table 按照固定模式排列控件
+ Gtk::Expander 一个可以隐藏子类的容器

#### 容器信号

+ add
+ check-resize
+ remove
+ set-focus-child

