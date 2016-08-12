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