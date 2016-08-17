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

为包装集里所有元素的 name 特性设置传递进来的值

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