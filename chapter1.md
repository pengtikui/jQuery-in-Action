## jQuery 基本原理

> `$()` 函数为 `jQuery()` 函数的别名

### jQuery 包装器

jQuery 支持 CSS 和 CSS 3 中使用的常见选择器

用法为：`$(selector)` 或 `jQuery(selector)`

### 实用工具函数

`$()` 函数可以作为几个通用的实用工具函数的命名空间前缀，对于大多数页面来说，很少用到，但是在编写 jQuery 插件时会用到

例如，删除字符串前后空格的实用工具函数：`$.trim(someString)`

### 文档就绪处理程序

`window.onload = function() {};` 用于在整个页面完全加载之后执行语句，不仅是在构建 DOM 树之后，也是在所有图片及外部资源完整地加载并且页面在浏览器窗口显示完毕之后。

jQuery 提供了一种简单的方法，让 DOM 树加载完成后就去执行代码：`$(document).ready(function() {});`

### 创建 DOM 元素

通过给 `$()` 函数传递包含 HTML 标记的字符串，就可以即时创建相应的 DOM 元素，如：`$("<p>Hello World!</p>")`