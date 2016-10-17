## 浏览器的事件模型

### DOM 第 0 级事件模型

### DOM 第 2 级事件模型

### IE 事件模型

> 以上内容参考：http://pengtikui.cn/javascript-event/

## jQuery 事件模型

除了明显不支持捕获阶段以外，jQuery 事件模型的功能集与第 2 级模型的功能集极为相似。

### 利用 jQuery 绑定事件处理程序

#### bind(eventType, data, listener)

在匹配集的所有元素上建立函数，作为指定事件类型的事件处理程序

eventType （字符串）为事件类型的名称

data （对象）为调用者提供的数据，可省略

listener （函数）为事件处理的函数

```javascript
$('img').bind('click', function() {alert('Hi There!');});
```

jQuery 链允许在单个语句里面应用多个命令 -- 各 bind() 命令在元素上分别建立相应的事件处理程序

#### eventTypeName(listener)

建立已指定的函数，作为与方法同名的事件类型的事件处理程序

#### one(eventType, data, listener)

bind() 的特殊版本，在匹配集的元素上建立作为指定事件类型的事件处理程序的函数，一旦执行，处理程序就会被自动删除

### 删除事件处理程序

通常事件处理程序被建立，就在页面的剩余生命周期里一直有效，one() 命令能够自动删除事件处理程序，但我们也可以在自己的控制下删除。

#### unbind(eventType, listener) / unbind(event)

从包装集的所有元素中删除可选的已传递参数所指定的事件处理程序，如果不提供参数，则从元素中删除所有的监听器（即事件处理程序）。

eventType （字符串）如果提供，则说明只删除为指定的事件类型而建立的监听器

listener （函数）如果提供，则标识将要删除的特定监听器

event （事件）删除触发 Event 实例所描述事件的监听器

