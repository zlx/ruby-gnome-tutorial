# Summary

* [README.md](README.md)
* [GTK2](gtk2/tut-gtk.md)
    * [介绍](gtk2/tut-gtk-preface.md)
   
    * [开始](gtk2/tut-gtk-intro.md)
      * [Hello World](gtk2/tut-gtk-helloworld.md)
      * [理解信号和回调机制](gtk2/tut-gtk-signals.md)
      * [事件](gtk2/tut-gtk-events.md)
      * [深入理解 Hello World](gtk2/tut-gtk-helloworld-details.md)
   
    * 继续
      * [更多关于信号的处理](gtk2/tut-gtk-signals-more.md)
      * [升级版的 Hello World](gtk2/tut-gtk-helloworld2.md)
   
    * [包装控件](gtk2/tut-gtk2-packing.md)
      * [理解包装的盒子](gtk2/tut-gtk2-packing-theory.md)
      * [关于这个盒子](gtk2/tut-gtk2-packing-box-details.md)
      * [一个包装的实例](gtk2/tut-gtk2-packing-demo.md)
      * [使用表格包装](gtk2/tut-gtk2-packing-tables.md)
      * [表格式包装实例](gtk2/tut-gtk2-packing-tables-demo.md)
   
    * [(3) 容器控件](gtk2/tut-gtk2-contwidg.md)
      * [(基于 Andrew Krause 的书[《Foundations of GTK+ Development》](http://www.gtkbook.com/))](gtk2/tut-gtk2-contwidg.md) 
        * [装饰容器](gtk2/tut-gtk2-contwidg-dc.md)
        * [布局容器](gtk2/tut-gtk2-contwidg-lc.md)
	  * [垂直和水平的盒子](gtk2/tut-gtk2-contwidg-hvbox.md)
	  * [垂直和水平的面板](gtk2/tut-gtk2-contwidg-hvpane.md)
	  * [表格](gtk2/tut-gtk2-contwidg-tables.md)
	  * [固定的容器](gtk2/tut-gtk2-contwidg-fixedcont.md)
	  * [扩展器](gtk2/tut-gtk2-contwidg-expanders.md)
	  * [处理盒子](gtk2/tut-gtk2-contwidg-handlebox.md)
	  * [记事本](gtk2/tut-gtk2-contwidg-notebooks.md)
	  * [事件盒子](gtk2/tut-gtk2-contwidg-eventbox.md)
	
	* [(4) 基本控件](gtk2/tut-gtk2-btt.md)
	
	   * [4.1 开关按钮](gtk2/tut-gtk2-btt-toggle.md)
	   * [4.2 多选按钮](gtk2/tut-gtk2-btt-check.md)
	   * [4.6 单选按钮](gtk2/tut-gtk2-btt-radio.md)
	   * [4.7 ** 不是按钮但是和按钮隐性相关的](gtk2/tut-gtk2-btt-bttbox.md)  
	   * [4.8 ** Font 按钮(在选择器下面...)（!）](gtk2/tut-gtk2-fichoo-fontbtt.md)
	   * [4.9 数字和文本数据输入](gtk2/tut-gtk2-numtxt.md)
	     * [4.10 单行输入框](gtk2/tut-gtk2-numtxt-entry.md)
	     * [4.11 旋转按钮](gtk2/tut-gtk2-numtxt-spinbttns.md)
	     * [4.12 垂直和水平方向放大](gtk2/tut-gtk2-numtxt-hvscales.md)
	   * [4.13 选择器接口和控件](gtk2/tut-gtk2-selchoose.md)
	     * 4.15 文件选择按钮
	     * 4.16 颜色按钮
	       * 4.16.1 修改一个控件的前景色
	     * 4.17 Font 按钮(!)                                          ⚠️  
	   * 4.18 测试一下
	
	+ (5) 对话框
	
	   + 创建你的对话框
	     + 模态框和非模态框
	     + ** GTK::Image 控件
	   + 消息对话框
	   + 关于你的应用程序
	     + ** Pixbuf
	     + 帮助菜单选项
	   + 文件选择对话框的类型
	     + 保存文件
	     + 创建目录(!)                                              ⚠️
	     + 选择多个文件
	   + 用字体和颜色选择对话框收集信息
	     + 颜色选择对话框
	     + 字体选择对话框
	     + 编程方式修改字体
	   + 使用 Gtk::Assistant 实现多页对话框
	     + 进度条
	   + 测试一下你看懂了没有
	           
	+ (6) GLib 简短介绍
	
	   + 环境变量
	   + 定时器
	   + 文件操作
	     + 错误处理
	   + 主循环
	   + 输入输出通道
	     
	+ (7) 文本视图控件
	
	   + 7.1 滚动窗口
	   + 7.2 文本视图
	     + 7.2.1 文本缓冲区
	     + 7.2.2 文本视图属性
	     + 7.2.3 Pango 标签阵列
	   + 7.3 文本迭代器和标记
	     + 7.3.1 编辑文本缓冲区(!,f)
	     + 7.3.2 检索文本迭代器和标记
	     + 7.3.3 修改文本缓冲区内容
	     + 7.3.4 剪切，复制和粘贴
	     + 7.3.5 在文本缓冲区搜索
	     + 7.3.6 文本缓冲区的滚动
	   + 7.4 文本标签
	   + 7.5 插入图片
	   + 7.6 插入子控件
	   + 7.7 GtkSourceView
	   + 7.8 测试一下你看懂了没有
	       
	+ (8) 树形视图控件
	
	   + 8.1 树形视图部分
	     + 8.1.1 Gtk::TreeModel
	     + 8.1.2 Gtk::TreeViewColumn 和 Gtk::CellRenderer
	     + 8.1.3 Gtk::ListStore 的使用
	     + 8.1.4 渲染和列
	       + 8.1.4.1 不要混淆模型的列和视图的列
	       + 8.1.4.2 TreeViewColumn 和 CellRenderer
	     + 8.1.5 创建 Gtk::ListStore
	     + 8.1.6 树形视图的排列
	   + 8.2 使用 Gtk::TreeStore
	     + 8.2.1 用树形存储组织内容
	       + 8.2.1.1 构建一个多层树形存储
	     + 8.2.2 单元格数据函数
	     + 8.2.3 多层树形存储
	       + 8.2.3.1 加载多层树形存储
	     + 8.2.4 Multi-item Super Columns
	   + 8.3 行的引用
	     + 8.3.1 树形路径
	     + 8.3.2 树形迭代器
	     + 8.3.3 树形行引用
	   + 8.4 添加行和选择处理
	     + 8.4.1 单项选择
	     + 8.4.2 多项选择
	     + 8.4.3 添加新行
	     + 8.4.4 组合框
	     + 8.4.5 移除多行
	   + 8.5 可编辑文本渲染器
	   + 8.6 单元格数据函数
	   + 8.7 单元格渲染
	     + 8.7.1 开关按钮渲染
	       + 8.7.1.1 渲染开关按钮可能影响树形视图里面其它值
	       + 8.7.1.2 树形视图中行列之间的数据依赖
	     + 8.7.2 Pixbuf 渲染
	     + 8.7.3 旋转按钮渲染
	     + 8.7.4 组合框渲染
	       + 8.7.4.1 进度条渲染
	     + 8.7.5 键盘加速渲染                                            ⚠️           
	    
	+ (9) 菜单和工具栏
	
	   + 9.1 弹出菜单
	     + 9.1.1 创建弹出菜单（!）                                        ⚠️
	       + 9.1.1.1 菜单项分割
	       + 9.1.1.2 弹出菜单回调
	   + 9.2 键盘快捷键
	     + 9.2.1 快捷键路径
	   + 9.3 状态栏
	     + 9.3.1 状态栏提示
	     + 9.3.2 状态栏控件
	       + 9.3.2.1 状态栏内容和消息
	     + 9.3.3 菜单项信息
	   + 9.4 菜单项
	     + 9.4.1 子菜单
	       + 9.4.1.1 构建菜单树机制
	         + 9.4.1.1.1 撤销菜单项（!）                                  ⚠️
	       + 9.4.1.2 子菜单的信号处理和回调
	         + 9.4.1.2.1 基于菜单项的哈希表的菜单程序设计及回调
	     + 9.4.2 不同类型菜单项的区别
	       + 9.4.2.1 图片菜单项
	       + 9.4.2.2 多选菜单项
	       + 9.4.2.3 单选菜单项
	   + 9.5 菜单栏
	     + 9.5.1 给菜单项添加键盘快捷键
	     + 9.5.2 键盘快捷键和它们关联菜单和其它控件
	       + 9.5.2.1 使用菜单中的快捷键路径
	   + 9.6 工具栏
	     + 9.6.1 一些 'toolbar-item-menu.rb' 范例须知
	       + 9.6.1.1 工具栏样式
	       + 9.6.1.2 你工具栏上的图标大小
	     + 9.6.2 拖放工具栏
	       + 9.6.2.1 独立式工具栏实例
	         + 9.6.2.1.1 独立是工具栏的方向
	       + 9.6.2.2 在一个窗口里拖放工具栏
	   + 9.7 工具栏项
	   + 9.8 动态创建菜单
	     + 9.8.1 创建用户界面文件
	     + 9.8.2 加载用户界面文件
	       + 9.8.2.1 附件操作类型
	       + 9.8.2.2 占位
	   + 9.9 自定义 Stock Item(!)                                       ⚠️
	   + 9.10 测试一下你的看懂了没有               
	                    
	+ (10) 拖放
	
	   + 10.1 拖放介绍
	     + 10.1.1 识别拖放对象
	     + 10.1.2 拖放的原对象和目标对象
	       + 10.1.2.1 为什么拖放控件需要一个它们自己的 Gdk::Window
	       + 10.1.2.2 有三种不同的拖放源和目标构建场景
	   + 10.2 没有自己的 Gdk::Window 情况下设置拖放控件
	     + 10.2.1 把一个按钮拖到一个 Label 上
	       + 10.2.1.1 是时候使用面向对象范式了
	         + 10.2.1.1.1 拖放调试模块须知
	     + [(10.2.2) 9.6.2.2 在一个窗口内拖放工具栏]
	     + 10.2.2 在一个窗口内拖放工具栏（面向对象版本）
	       + 10.2.2.1 'dnd-toolbar-oo.rb' 编程实例须知
	   + 10.3 自带 Gdk::Window 的拖放控件
	     + 10.3.1 文本视图控件中的拖放
	     + 10.3.2 树形视图项的拖放
	       + 10.3.2.1 树形视图内建拖放机制
	       + 10.3.2.2 树形视图中自定义拖放
	     + 10.3.3 图标视图项的拖放
	       + 10.3.3.1 文本视图中自定义拖放
	     + 10.3.4 拖放到可绘画控件
	       + 10.3.4.1 Gtk::DrawingArea 上拖放
	       + 10.3.4.2 拖放和 Cairo
	                       
	+ (11) 其它 GTK+ 控件
	
	  + 绘画控件
	  + 日历
	  + 状态图标
	
	+ (12) 绘画区域和 Cairo
	
	  + 介绍
	  + 把绘画图写入到 Pixbuf 文件中
	
	+ (12.3) Ruby Cairo 教程(top page)
	
	  + 12.3.0 介绍 Ruby Cairo 教程
	    + 12.3.0.1 用 Gtk-Cairo 框架运行这个教程中的实例代码
	      + 12.3.0.1.1 Cairo 后端
	        + 12.3.0.1.1.1 编程须知
	          + 12.3.0.1.1.1.1 学生须知
	      + 12.3.0.1.2 运行任意 Cairo 代码的模版文件
	        + 12.3.0.1.2.1 一个运行 Cairo 代码的真实例子
	      + 12.3.0.2 在非 Gtk Ruby 环境运行 Cairo 代码
	      + 12.3.0.3 Hiki Gtk With Cairo Module Download File
	    + 12.3.1 Cairo 的绘画模型
	      + 12.3.1.1 名词
	        + 12.3.1.1.1 Destination
	        + 12.3.1.1.2 Source
	        + 12.3.1.1.3 Mask
	        + 12.3.1.1.4 Path
	        + 12.3.1.1.5 Context
	      + 12.3.1.2 动词
	        + 12.3.1.2.1 Stroke
	          + 12.3.1.2.1.A1 Scale
	          + 12.3.1.2.1.A2 默认放大的实例
	          + 12.3.1.2.1.A3 经验法则
	        + 12.3.1.2.2 Fill
	        + 12.3.1.2.3 显示文本 - Glyphs
	        + 12.3.1.2.4 Paint
	          + 12.3.1.2.4.A1 Ruby Cairo 库里涂料以及颜色透明度
	        + 12.3.1.2.5 Mask
	          + 12.3.1.2.5.A1 Ruby Cairo 库不支持渐变模式
	    + 12.3.2 用 Cairo 绘画
	      + 12.3.2.1 准备或者选择一个源
	      + 12.3.2.2 创建一个路径
	    + 12.3.3 理解文本
	    + 12.3.4 理解变换
	    + 12.3.5 下一步做什么？
	    + 12.3.6 技巧和窍门
	      + 12.3.6.1 行宽
	      + 12.3.6.2 文本对其
	
	+ (13) 动态的用户界面
	
	  + 创建用户界面的 Glade
	    + Glade 的窗口以及菜单
	  + 用 Glade 创建用户界面的实例
	    + 创建窗体
	    + 添加工具栏
	    + 添加文件查看器
	    + 做出一些改变
	    + 控件信号
	    + 创建菜单
	  + 使用 Libglade
	  + 测试一下你看懂了没有
	    + 动态菜单设计的问题
	    
	+ (A) 附录   
	  ＋ 计算机专业人员的数字颜色理论