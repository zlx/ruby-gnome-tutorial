## 选择器接口和控件

### 简短描述

所有这些控件都是所谓的选择器控件家族的成员。在 Gtk 文档中，你可以在 (File/Font/Color/Input Devices) 下面找到这些控件。这个家族被分成4块：

#### 颜色组

+ Gtk::ColorButton - 一个可以调出颜色选择窗口的按钮
+ Gtk::ColorSelection - 一个可以用来选择颜色的控件
+ Gtk::ColorSelectionDialog - 一个用来选择颜色的标准对话框

#### 字体组

+ Gtk::FontButton - 一个可以调出字体选择窗口的按钮
+ Gtk::FontSelection - 一个可以用来选择字体的控件
+ Gtk::FontSelectionDialog - 一个可以用来选择字体的对话框

#### 文件组

##### Gtk::FileChooser

  Gtk::FileChooser 模块只是一个接口，因此我们不会直接创建 FileChooser 实例。下面的列表是所有和 FileChooser 相关的类：
  
  + Gtk::FileChooser - Gtk::FileChooserWidget 和 Gtk::FileChooserDialog 使用的文件选择接口
  + Gtk::FileChooserButton - 一个可以调出文件选择窗口的按钮
  + Gtk::FileChooserDialog - 一个文件选择窗口，用于 File/Open 或者 File/Save 命令等
  + Gtk::FileChooserWidget - 一个可以嵌入其它控件的文件选择控件
  + Gtk::FileFiter - 一个用于选择文件子集的过滤器
  + Gtk::FileSelection - 提醒用户选择一个文件或者目录（废弃使用 Gtk::FileChooserDialog）
  
  为了更好的理解这些类的协同工作，我们需要有个例子可以放到你的系统中运行来体验。
  
##### Gtk::InputDialog

用来配置 XInput 扩展



    