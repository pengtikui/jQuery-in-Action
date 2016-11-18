# 用动画和效果来装扮网页

在给页面添加效果之前，必须思考这个问题：应该添加吗？滥用效果的页面会引起意想不到的反作用。效果应该是用来增强页面的可用性，而不是妨碍它。

### 显示和隐藏

#### hide(speed, callback)

使包装集里的元素变为隐藏状态。

* speed：效果持续时间，值可以为毫秒数，也可以是 slow、normal 或 fast 字符串，可选
* callback：回调函数，在动画完成时调用，可选

如果不带参数调用，就直接把元素的 `display` 属性设置为 `none`；如果提供 `speed` 参数，就在这个时间内将元素的大小和透明度捉奸降到 0，然后在将 `display` 属性设置为 `none`。

#### show(speed, callback)

使包装集里的元素显示。

参数的用法与 `hide()` 相同

#### toggle(speed, callback)

在隐藏的包装集元素上执行 `show()`，在非隐藏的包装集元素上执行 `hide()`。

参数的用法与 `hide()` 相同

### 淡入和淡出

#### fadeOut(speed, callback)

将非隐藏的任何已匹配元素的不透明度逐渐降到 0%，然后将 display 属性设置为 none。

* speed：效果持续的时间，值可以为毫秒数，也可以是 slow、normal 或 fast 字符串，默认为 normal，可选
* 回调函数，在动画完成时调用，可选

#### fadeIn(speed, callback)

通过把不透明度逐渐提高到初始值，使隐藏的任何已匹配元素显示出来。

参数的用法与 `fadeOut()` 相同

#### fadeTo(speed, opacity, callback)

从当前的设置到 opacity 所指定的新设置，调整元素的不透明度。

* speed：同 `fadeOut()`
* opacity：不透明度，取值范围从 0.0 到 1.0
* callback：同 `fadeOut()`

### 滑上和滑下

#### slideDown(speed, callback)

通过从上往下逐渐扩大元素的垂直面积，使隐藏的任何已匹配元素显示出来，非隐藏的任何元素不受影响。

参数的用法与 `fadeOut()` 相同

#### slideUp(speed, callback)

通过从下往上逐渐减小元素的垂直面积，最终使非隐藏的任何已匹配元素隐藏，即将 display 属性的值设置为 none。

参数的用法与 `fadeOut()` 相同

#### slideToggle(speed, callback)

在隐藏的元素上执行 `sildeDown()`，同时在非隐藏的元素上执行 `sildeUp()`。

参数的用法与 `fadeOut()` 相同

### 停止动画

#### stop()

停止当前正在进行的、已匹配的所有元素里的所有动画。

无参数

### 创建自定义的动画

#### animate(properties, duration, easing, callback)

* properties：一个散列对象，指定动画结束时所支持的 CSS 样式应该达到的终值
* duration：效果的持续时间，值可以为毫秒数，也可以是 slow、normal 或 fast 字符串，如果省略，则不产生动画
* easing：字符串，一个函数的名称，用来实现动画的缓和效果，可选。缓和函数必须通过名称注册，核心 jQuery 提供两个缓和函数 linear 和 swing
* callback：回调函数，动画完成时调用，可选

#### animate(properties, options)

* properties：同上
* options：一个散列对象，用来指定动画的参数值，所支持的属性如下：
    - duration：同上
    - easing：同上
    - complete：动画完成时调用的函数
    - queue：如果为 false，动画不会加入队列而立即开始运行
