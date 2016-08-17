## 操作元素属性和特性

### 操作元素属性

#### each(iterator)

遍历包装集里所有元素，为各元素分别调用传递进来的迭代器函数

以下命令可以把属性值设置到匹配集里的所有元素上：

```javascript
$('img').each(function(n) {
    this.alt = 'This is image [' +n+ '] with an id of ' + this.id;
});
```

### 获取特性值

#### attr(name)

获取指派到包装集里第一个元素指定特性的值

### 设置特性值

#### attr(name, value)

为包装集里所有元素的 name 特性设置传递进来的值，value 可接受对象或函数

#### attr(attributes)

把已传递对象指定的特性和值设置到包装集的所有元素上，attributes 是一个对象

这是设置多个特性到包装集里所有元素的快速简便的方式，如：

```javascript
$('input').attr(
    { value: '', title: '' }
);
```

### 删除特性

#### removeAttr(name)

从每个已匹配元素删除指定的特性

## 修改元素样式

### 添加和删除类名称

#### addClass(names)

添加指定的一个或多个类名称到包装集的所有元素

names 为一个字符串，多个类名用空格隔开

#### removeClass(names)

从包装集各元素里删除指定的一个或多个类名称

#### toggleClass(name)

如果在元素中指定类名称不存在，则添加指定的类名称；如果元素已拥有指定的类名称，则从元素中删除指定类名称

### 获取和设置样式

#### css(name, value)

设置指定的值到每个已匹配元素的指定的 CSS 样式属性，value 可接受函数

#### css(properties)

为所有已匹配元素设置已传递对象里多个键所指定的 CSS 属性为相关的值

#### css(name)

获取包装集里第一个元素 name 所指定 CSS 属性的已计算样式值

name 指定一个 CSS 属性名称，返回它的已计算样式值（字符串）

#### width 和 height

width(value)、height(value) 对匹配集里所有元素设置指定的宽度或高度，value 已像素为单位

width、height 获取包装集的第一个元素的宽度或高度，以数字类型返回

### 其他样式相关命令

#### hasClass(name)

匹配元素集里是否有元素拥有已传递 name 参数所指定的类名称，返回 true 或 false