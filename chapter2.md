## 选择将被操作的元素

### 利用基本 CSS 选择器

| 选择器 | 描述 |
| :--- | :--- |
| a | 匹配所有 `a` 标签元素 |
| #specialID | 匹配 id 为 specialID 的元素 |
| .specialClass | 匹配拥有 CSS 类 specialClass 的元素 |
| a#specialID.specialClass | 匹配 id 为 specialID、拥有 CSS 类 specialClass 的链接元素 |
| p a.specailClass | 匹配拥有 CSS 类 specialClass、在 p 标签内的链接元素 |

### 利用子选择器、容器选择器和特性选择器

| 选择器 | 描述 |
| :--- | :--- |
| * | 任何元素 |
| E | 标签名称为 E 的所有元素 |
| E F | 标签名称为 F、作为 E 的后代节点的所有元素 |
| E>F | 标签名称为 F、作为 E 的直接子节点的所有元素 |
| E+F | 前面是邻近兄弟节点 E 的所有元素 F（E 和 F 紧挨着） |
| E~F | 前面是任何兄弟节点 E 的所有元素 F（E 和 F 可以不紧挨着） |
| E:has(F) | 标签名称为 E、至少又一个标签名称为 F 的后代节点的所有元素 |
| E.C | 带有类名 C 的所有元素 E，.C 等效于 *.C |
| E#I | id 特性值为 I 的所有元素 E，#I 等效于 *#I |
| E[A] | 带有特性 A 的所有元素 E（不管特性 A 的值是什么 |
| E[A=V] | 所有元素 E，其特性 A 的值正好是 V |
| E[A^=V] | 所有元素 E，其特性 A 的值以 V 开头 |
| E[A$=V] | 所有元素 E，其特性 A 的值以 V 结尾 |
| E[A*=V] | 所有元素 E，其特性 A 的值包含 V |

### 通过位置选择

| 选择器 | 描述 |
| :--- | :--- |
| :first | 页面的最先的匹配 |
| :last | 页面的最后的匹配 |
| :first-child | 最先的子元素 |
| :last-child | 最后的子元素 |
| :only-child | 返回没有兄弟节点的所有元素 |
| :nth-child(n) | 第 n 个子节点，n 从 1 开始 |
| :nth-child(even|odd) | 偶数或奇数的子节点 |
| :nth-child(Xn+Y) | 根据传入的公式计算的第 n 个子节点 |
| :even 或 :odd | 页面范围内偶数或奇数的匹配元素 |
| :eq(n) | 第 n 个匹配元素，n 从 0 开始 |
| :gt(n) | 第 n 个匹配元素（不包括）之后的元素，n 从 0 开始 |
| :lt(n) | 第 n 个匹配元素（不包括）之前的元素，n 从 0 开始 |

> `:first` 和 `:last` 比较晕！

### 利用自定义 jQuery 选择器

| 选择器 | 描述 |
| :--- | :--- |
| :animated | 当前处于动态控制之下的元素 |
| :button | 任何按钮（input[type=submit]、input[type=reset]、input[type=button] 或 button） |
| :checkbox | 复选框元素（input[type=checkbox]） |
| :checked | 已选中的复选框或单选按钮 |
| :contains(foo) | 包含文本 foo 的元素 |
| :disabled | 在界面上已禁用的表单元素 |
| :enabled | 在界面上已启用的表单元素 |
| :file | 文件元素（input[type=file]） |
| :header | 标题元素，h1 ~ h6 |
| :hidden | 隐藏的元素 |
| :image | 表单图像元素（input[type=image]） |
| :input | 表单元素，input、select、textarea、button |
| :not(filter) | 根据指定的筛选器进行求反 |
| :parent | 拥有后代节点（包括文本）的元素 |
| :password | 口令元素（input[type=password]） |
| :radio | 单选按钮元素（input[type=radio]） |
| :reset | 复位按钮元素（input[type=reset] 或 button[type=reset]） |
| :selected | 已选中的选项元素 |
| :submit | 提交按钮元素（input[type=submit] 或 button[type=submit]） |
| :text | 文本字段元素（input[type=text]） |
| :visible | 可见的元素 |

## 生成新 HTML

创建空 <div> 元素，`$("<div></div>")`、`$("<div>")` 和 `$("</div>")` 均可，不过后两者不可用于创建 <script> 元素

`$("<div></div>").appendTo("#id");`

## 管理包装元素集合

### 确定包装集的大小

#### size()

返回包装集里面元素的个数，无参数

`$("a").size()`

### 从包装集获取元素

jQuery 允许把包装集当成 JavaScript 数组进行处理

例如获取页面上带有 alt 特性的所有 <img> 元素的集合中的第一个：`$('img[alt]')[0]`

#### get(index)

获取包装集里的一个或所有匹配元素，如果不指定参数，包装集里的所有元素就以 JavaScript 数组形式返回；如果指定了下标参数，就返回下标所对应的元素

index 参数（数值）用于指定将被返回的单个元素

#### index(element)

在包装集里查找传入的元素，并返回该元素在包装集里的顺序下标；如果该元素不存在，则返回 -1

### 筛选元素包装集

#### add(expression)

把表达式参数所指定的元素添加到包装集，表达式可以是选择器、HTML 片段、DOM 元素或 DOM 元素数组，返回包装集

* 想要匹配带有 alt 或 title 特性的所有 <img> 元素，语句为：`$('img[alt]').add('img[title]')`，不过也可以这么写：`$('img[alt], img[title]')`

* 想要给带 alt 特性的所有 <img> 元素添加一个 CSS 类 class1，然后给带 alt 或 title 特性的所有 <img> 元素添加一个 CSS 类 class2，语句为：`$('img[alt]').addClass('class1').add('img[title]').addClass('class2')`

> add() 方法把多个选择器链在一起形成“或”关系

#### not(expression)

根据表达式参数的值，从包装集里删除元素

* 想要选择页面里带有 title 特性的 <img> 元素，除 title 特性值包含文本 puppy 的元素，语句为：`$('img[title]').not('[title*=puppy]')`
* 传递给 not() 方法的选择器仅限于删除任何元素引用的筛选表达式，not() 方法不支持元素选择器，元素选择器包含具体元素类型的名称，如 `img[title*=puppy]`，筛选选择器的特征以 `[` 或 `:` 开头

> not() 方法把多个选择器链在一起形成“与非”关系

#### filter(expression)

利用传入的选择器表达式或筛选函数，从包装集里筛选元素

如果参数是字符串，则指定 jQuery 选择器，从包装集里删除所有与选择器不匹配的元素；如果参数是一个函数，函数返回值为 false 的任何元素都会从包装集中删除

* 创建包含数字值的所有 <td> 元素的包装集：`$('td').filter(function() {return this.innerHTML.match(/^\d+$/)})`

#### slice(begin, end)

创建并返回新包装集，新包装集包含原包装集的连续的一部分，begin 和 end 均为数字，end 可选

* `$('*').slice(2,3)` 选择页面上所有元素，然后生成包含原包装集的第 3 个元素的包装集，注意，与 `$('*').get(2)` 不同，后者返回包装集里的第 3 个元素，而不是包含元素的包装集