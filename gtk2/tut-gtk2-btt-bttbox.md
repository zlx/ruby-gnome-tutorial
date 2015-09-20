## 按钮和开关

就像标题所说，这些控件并不是按钮，但是有一些处理按钮所需要的功能。

	Gtk::Bin
	|   Gtk::Window
	|   |   Gtk::Button
	|   |   |   Gtk::ToggleButton
	|   |   |   |   Gtk::CheckButton
	|   |   |   |   |   Gtk::RadioButton
	|   |   |   Gtk::ColorButton
	|   |   |   Gtk::FontButton
	|   |   |   Gtk::LinkButton
	|   |   |   Gtk::OptionMenu
	|   |   |   Gtk::ScaleButton
	|   |   |   |   Gtk::VolumeButton
	Gtk::Box
	|   Gtk::ButtonBox
	|   |   Gtk::HButtonBox
	|   |   Gtk::VButtonBox

上述继承树清晰地表示出了两种继承关系。这两者的关系在于这些盒子是用来放置按钮的。 Gtk::ButtonBox 存在的主要目的是包含 Gtk::HButtonBox 和 Gtk::VBottonBox 控件的属性。

一旦用 Gtk::HButtonBox.new 或者 Gtk::VButtonBox.new 创建了按钮盒子，你就需要为盒子里面的按钮设置布局样式，你可以使用下面的方法完成：

+ Gtk::ButtonBox#layout_style － 查看按钮盒子里面组织按钮的方式
+ Gtk::ButtonBox#layout_style＝(style) － 修改按钮盒子组织按钮的方式
+ Gtk::ButtonBox#set_layout_style(style) － 同 Gtk::ButtonBox#layout_style= 一样

在上面的方法调用中，可选的参数是以下几种：

#### Gtk::ButtonBox 样式

用来指定 Gtk::ButtonBox 中组织它包含的按钮的方式：

+ DEFAULT_STYLE － 默认布局
+ SPREAD - 均匀分布按钮
+ EDGE - 按钮分布在盒子边缘
+ START - 按钮被放置子盒子的开端（水平盒子的左边，垂直盒子的上面）
+ END - 按钮被放置在盒子的末端（水平盒子的右边，垂直盒子的下边）
+ CENTER

最好，你可以使用 Gtk::ButtonBox#add_child 来添加子类。