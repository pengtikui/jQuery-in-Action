## 操作元素属性和特性

### 操作元素属性

#### each(iterator)

遍历包装集里所有元素，为各元素分别调用传递进来的迭代器函数

以下命令可以把属性值设置到匹配集里的所有元素上：

```javascript
$('img').each(function(n) {
    this.alt = 'This is image [' +n+ '] with an id of ' + this.id;
});