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

## 设置元素内容

### 替换 HTML 或文本内容

#### html()

获取匹配集里第一个元素的 HTML 内容，无参数

#### html(text)

把传入的 HTML 片段设置位所有匹配元素的内容，text 为将被设置为元素内容的 HTML 片段

#### text()

把包装集里元素的所有文本内容连接起来，并返回字符串作为命令的结果

假如有 HTML 片段：

```html
<ul id="theList">
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
    <li>Four</li>
</ul>
```

语句 `var text = $('#theList').text();` 使变量 `text` 赋值为 OneTwoThreeFour

#### text(content)

把所有已包装元素的文本内容设置为已传递值，如果已传递文本包含尖括号，则这些字符被替换为等价的 HTML 实体

### 移动和复制元素

#### append(content)

把传入的 HTML 片段或元素追加到所有已匹配元素的内容之后

语句 `$("p.appendToMe").append($("a.appendMe"))` 把带有类 appendMe 的所有链接追加到带有类 appendToMe 的 `<p>` 元素

> 对原始元素的布置取决于追加目标的元素的数量，如果是单一的目标，则元素执行把原始元素**移动**到新父元素的操作，如果有多个目标，则执行复制操作

#### appendTo(target)

把包装集里所有元素移动到指定目标的内容的末尾

如果目的地只标识一个目标元素，则元素被移动；如果目的地标识多个目标元素，则源元素被复制

#### prepend() 和 prependTo()

像 append() 和 appendTo() 那样执行，不过是在目标元素的内容之前插入源元素

#### before() 和 insertBefore()

在目标元素之前插入元素，而不是在目标元素的第一个子元素之前

#### after() 和 insertAfter()

在目标元素之后插入元素，而不是在目标元素的最后一个子元素之后

### 包裹元素

#### wrap(wrapper)

把匹配集各元素用已传递 HTML 标签或已传递元素的克隆副本分别包裹起来

语句 `#("a.surprise").wrap("<div class='hello'></div>")` 把带有 surprise 类的各链接分别包裹在带有类 hello 的 div 里

语句 `$("a.surprise").wrap($("div:first")[0])` 用页面上第一个 div 元素的克隆副本分别包裹各链接

#### wrapAll(wrapper)

用已传递元素的克隆副本或已传递 HTML 标签，把匹配集的元素作为一个单元包裹起来

#### wrapInner(wrapper)

用已传递元素的克隆副本或已传递 HTML 标签，把匹配集个元素的内容（包括文本节点）分别包裹起来

### 删除元素

#### remove()

从页面 DOM 里删除包装集里所有元素，无参数

#### empty()

清空匹配集里所有 DOM 元素的内容

利用 remove() 和 after() 命令来实现替换操作：

```javascript
$("div.elementToReplace").after("<p>I am replacing the div</p>").remove();
```

新建的 p 元素替换了原始 div 元素

### 克隆元素

#### clone(copyHandlers)

创建包装集里元素的副本，并返回包含这些副本的新包装集，元素及其任何后代元素都被复制，事件处理程序是否被复制，取决于参数 copyHandlers 的设置

copyHandlers 为布尔型，如果为 true，复制事件处理程序；如果为 false 或省略，则不复制事件处理程序

### 处理表单元素值

#### val()

返回匹配集里第一个元素的 value 特性，如果是多选元素，则返回所有选中项的数据

#### val(value)

把传入的值设置为所有已匹配表单元素的值

value 参数为一个字符串

#### val(values)

导致包装集里任何复选框、单选按钮或 select 元素的选项变为已选中（checked）或已选择（selected）状态，只要他们的值和已传递值数组的任何一个值相匹配

values 参数为一个值数组