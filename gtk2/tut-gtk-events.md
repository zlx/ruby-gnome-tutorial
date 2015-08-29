### 事件

除了上面的信号机制外，X Window Server 的事件也在 GTK 中有所体现。

这里有一个详细的可捕获事件列表：

+ event
+ button_press_event
+ button_release_event
+ scroll_event
+ motion_notify_event
+ delete_event
+ destroy_event
+ expose_event
+ key_press_event
+ key_release_event
+ enter_notify_event
+ leave_notify_event
+ configure_event
+ focus_in_event
+ focus_out_event
+ map_event
+ unmap_event
+ property_notify_event
+ selection_clear_event
+ selection_notify_event
+ proximity_in_event
+ proximity_out_event
+ visibility_notify_event
+ client_event
+ no_expost_event
+ window_state_event

你可以用之前使用的处理 GTK 信号的方式来处特定的 X11 事件。只需要把信号名字改成上面提到的事件名字。

    GLib::Instantiatable#signal_connect("event name") do
	    # Code to execute upon reception of "event name".
	end

这个回调可以接受两个参数：

    GLib::Instantiatable#signal_connect("event name") do |w, e|
	    # ...
	end

这里， w 代表这个空间，e 代表这个事件。

GTK 会根据这段代码的返回值来决定这个事件要不要继续传递：

+ 如果是 true， GTK 会在这里停止
+ 如果是 false， GTK 会继续传播这个事件

同样， GDK 选择和拖放也会触发一些事件，但表现为 GTK 信号：

+ selection_received
+ selection_get
+ drag_begin_event
+ drag_end_event
+ drag_data_delete
+ drag_motion
+ drag_drop
+ drag_data_get
+ drag_data_received
