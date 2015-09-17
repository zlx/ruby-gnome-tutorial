## 基本控件

### 按钮和开关

+ 开关按钮
  + 助记符
+ 多选按钮
  + 使用 Stock Items
  + 回调盒事件处理
+ 单选按钮
+ ** 不是按钮但是和按钮隐性相关的  
+ ** Font 按钮(在选择器下面...)


### 简要介绍

Gtk+ 你能找到很多名字里面包含 Button 的控件，但是主要的按钮控件并不多。下面就是所有按钮控件的列表，在 Gtk 文档里面你也能在相同的标题（Buttons and Toggles）下面找到它们：

+ Gtk::Button - 一个会在点击时候创建一个信号的控件
+ Gtk::CheckButton - 创建有多个离散的开关按钮的控件
+ Gtk::RadioButton - 一个从多个选择的控件
+ Gtk::ToggleButton - 创建可以保持状态的按钮
+ Gtk::LinkButton - 创建绑定一个URL的按钮

下面是按钮的继承树：

	GtkButton
	|   GtkToggleButton
	|   |   GtkCheckButton
	|   |   |   GtkRadioButton
	|   GtkColorButton
	|   GtkFontButton
	|   GtkLinkButton
	|   GtkOptionMenu
	|   GtkScaleButton
	|   |   GtkVolumeButton

上面提到的部分按钮会在之后的章节中介绍

   
   