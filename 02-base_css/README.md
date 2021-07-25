# css

## 简介(01-css.html)
- 1. css: 级联样式表
- 2. css写在`<head>`的`<style>`标签中

## 初体验(01-css.html)
- 1. 元素选择器: `xxx {}`, 选中元素. 如:`p {color: red;font-size: 48px;}`是修改`<p></p>`的样式. 
- 2. 类选择器: `.xxx {}`, 选中类. 如:`.cla {color: red;font-size: 48px;}`是修改`<p class="cla"></p>`的样式. 
- 3. id选择器: `#xxx {}`, 选中id. 如:`#cla {color: red;font-size: 48px;}`是修改`<p id="cla"></p>`的样式. 
- 4. 通配符选择器: `* {}`, 选中所有对象.
## 类选择器(01-css.html)
- 1. 类选择器覆盖元素选择器
- 2. 支持多类, 多个类名用空格隔开, 如: `<div class="red px35">一个div</div>`
- 3. 类选择器是用得最多的

## id选择器(01-css.html)
- 1. 元素的id是唯一的

## 通配符选择器(none)
- 1. 注意, 它不是正则
- 2. 特殊情况才使用

## 字体属性(02-font-style.html)
- 1. `font-family`: 可以写多个字体, 根据系统知否安装字体从前到后依次选择
- 2. `font-size`: npx
- 3. `font-wight`: 字体粗细. 实际开发之中推荐使用数字
- 4. `font-style`: 
- 5. `font`: 可以连写(复合属性), 连写时顺序有要求, 连写(复合)用以节省码量
- 6. `color`: 有多种写法: `deeppink`(预定义的颜色值) `#ff0000`(十六进制, 用得最多) `rgb(255, 0, 0)`(RGB)
- 7. `text-align`: 水平对齐方式, 相对于其标签元素
- 8. `text-decoration`: 装饰文本
- 9. `text-indent`: 首行缩进, `em`, 相对于当前文字元素的大小
- 10. `line-height`: 行间距
- 11. 有量像素的工具

## css引入方式(其实就是css写在了哪里)(03-css-import.html)
- 1. 行内样式表: 写在元素内, 一个demo: `<p style="font-weight: bold;"></p>`
- 2. 内部样式表: 放在html文件中, 理论上可以放在html任意位置, 但一般放在`<head>`中. 控制当前html的元素样式.
- 3. 外部样式表: css单独成文件. 一般用这种方式. css文件中只有样式没有标签. 通过`<link>`在html中引入. 一个demo: `<link rel="stylesheet" href="p2.css">`

## chrome调试工具
- 1. F12打开调试工具
- 2. 可以检查元素/样式/样式错误/样式内属性错误. 

## emmet语法, 简写, 面向编辑器, vscode支持, 输入完之后按tab补全(提高html/css写代码速度)(04-emmet.html)
- 1. `!`, 生成html代码框架
- 2. `div*10`, 生成10个div
- 3. 类似的, `p*10`, 生成10个p
- 4. 包含标签, `div>span`, 生成`<div><span></span></div>`, 注意里边的`>`符号
- 5. 并列标签, `div+span`, 生成`<div></div>\n<span></span>`, 注意里边的`+`符号
- 6. 并列标签, `div+span`, 生成`<div></div>\n<span></span>`, 注意里边的`+`符号
- 7. `.nav`, 生成`<div class="nav"></div>`
- 8. `#nav`, 生成`<div id="nav"></div>`
- 9. `p.nav`, 生成`<p class="nav"></p>`
- 10. `ul>li#nav`, 生成`<ul>\n<li id="nav"></li>\n</ul>`, 即支持级联
- 11. `.nav$*5`, 生成:
    ```html
    <div class="nav1"></div>
    <div class="nav2"></div>
    <div class="nav3"></div>
    <div class="nav4"></div>
    <div class="nav5"></div>
    ```
- 12. `div{HAHAHAHAHA}`, 生成:`<div>HAHAHAHAHA</div>`
- 13. css样式中, 首字母+tab补全, 如: `tac`+tab键: `text-align: center;`
- 14. 再如: `w100`+tab键: `width: 100px;`

## 快速格式化, 针对vscode
- 1. ctrl+shit+i: 手动格式化
- 2. 还支持自动格式化, 需要在setting中设置, 但我更偏向手动格式化

## 复合选择器(05-composite.html)
- 1. 后代选择器, 如`ol li {color: red;}` 会选中`ol`的子元素`li`
    - 后待选择器也能选中孙子, 如:  `ul span {color: green;}` 会选中如下代码的`中`
        ```html
        <ul>
            <li>我在ul中</li>
            <li>我在ul中</li>
            <li>我在ul中</li>
            <li>我在ul中</li>
            <li>我在ul<span>中</span></li>
        </ul>
        ```
    - 后代选择器支持类(`class`), `id`
- 3. 子元素选择器(不同于后代选择器) 使用`>`, 自会选中子代, 不会选中孙代, 如: `.case > span {color: pink;}`
        ```html
        <div class="case">
            <!-- 不会被选中 -->
        <span>儿子</span>
        <div>
            <!-- 会被选中 -->
            <span>孙子</span>
        </div>
        </div>
        ```
- 4. 并集选择器, 使用`,`, 如: `.case3, .case4 {color: red;}`会选中: 
        ```html
        <div class="case3">
            case3
        </div>
        <div class="case4">
            case4
        </div>
        ```
    - 注意, 并集选择器一般竖着写
- 5. 链接伪类选择器(相当于条件判断选择器? 可以用js实现吧? )
    - 面向链接元素
    - `a:link`/`a:visited`/`a:hover`/`a:active`
    - 多个伪类选择器有顺序要求, 需按上述顺序排列
    - 一般`a:hover`用得比较多
- 6. `:focus`伪类选择器
    - 获得光标生效, 失去光标失效

## 元素的显示模式(是横排还是纵排)(06-element_trans.html)
- 1. 块级元素: 自己独占一行的元素. 包括: `<h1>`~`<h6>`, `<p>`, `<div>`, `<ul>`, `<ol>`, `<li>`
    - 没有指定宽度的话继承父亲的宽度
    - 当然也可以给宽度, 给完宽度还是独占一行 
    - 文字类元素(如`<p>`)内不能放块元素
- 2. 行内元素(有时被称为内联元素): 与其他行内元素共享行. 包括: `<span>`, `<strong>`, `<b>`等
    - 行内元素无法设置宽/高
    - 行内元素只能放其他行内元素或者文本元素, 特殊情况下`<a>`中可以放块级元素
    - 链接中不能再放链接
- 3. 行内块元素: `<img />`, `<input />`, `<td />`
    - 相邻行内块元素在一行上, 但之间会有间隙
    - 可以设置宽/高
- 4. 某些情况下元素的显示模式可以转换 
    - `display: block` 把行内元素转成块级元素(重要)    
    - `display: inline` 把块级元素转成行内元素    
    - `display: inline-block` 把x转成行内块元素(重要)   
## snipaste 截图工具
- 1. 回头看/小技巧
    - `text-indent`, 首行缩进
    - 单行文字居中方法: `line-height==height`, 妙啊

## css背景属性(07-css-background.html)
- 1. `background-color`: 背景颜色, 默认是transparent(透明)
- 2. `background-image`: 背景图片 
    - 如`background-image: url(g.jpg);`, 不要忘记`url()`
    - 尺寸不对的话默认是裁剪
- 3. `background-repeat`: 背景平铺, 修饰背景图片的格式
- 4. `background-position`: 改变背景图片的位置, 单位可以是方位名词/精确单位/混合单位
- 5. `background-attachment`: 视察滚动效果
- 6. 复合写法: `background: black url() no-repeat fixed center top`, 实际开发中更推荐这种写法
- 7. 背景色半透明, 如: `background: rgba(0, 0, 0, 0.3);`

## css的3大特性
- 1. 就近性
    - 就近原则(解决样式冲突的问题)(同类选择器)
- 2. 继承性
    - 子元素继承父元素的样式
    - `font: 12px/1.5` 当前1.5表示行高为当前文字大小的1.5倍
- 3. 优先级
    - 优先级是有规则的: 继承或者`*`< 元素选择器 < 类, 伪类选择器 < ID选择器 < 行内样式(`style=""`) < `!important`
    - `<a>`默认是有样式的
    - 复合选择器会有权重叠加的现象, 不会有进位

## 盒子模型(08-box_model.html)
- 1. 网页的本质就是摆盒子
- 2. 盒子的组成: 边框border/内容content/内边距padding/外边距margin
- 3. 边框border
    - `border-width`/`border-style`/`border-color`
    - 复合写法: 如: `border: 1px solid red`, 没有顺序要求, 一般按这样的顺序写   
    - `border-top/bottom/left/right`分别指定4边框, 如: `border-top: 1px solid red` 
    - 表格的细线边框, 重点是使用`border-collapse`
    - 边框是往外扩展的(不是往里边扩展的)
- 4. 内边距padding
    - `padding-top/bottom/left/right`
    - `padding`的复合写法
    - `padding`也是向外扩展的, 即`padding`也会影响盒子的实际大小
    - 设置`padding`的话可以根据内容调节盒子的大小
    - 盒子本身没有width/height, 那么padding不会撑开width/height
- 5. 外边距margin
    - `top/bottom/left/right`
    - 复合写法, 和`padding`类似
    - 外边距合并, 嵌套的盒子的边框开始问题, 比如若子盒子和父盒子margin设置的相同的值, 则子盒子和父盒子边缘重合, 解决方法: 父盒子设置边框/父盒子设置内边距/父盒子加上`overflow: hidden`/等等
- 6. 清除内外边距
    - 一些网页元素自带内外边距, 用通配符选择器(`*`)可以归零
- 7. 注意
    - 行内元素设置上下内外边距无效, 若想设置上下内外边距, 转为块级元素或者行内块元素

## PS的基本操作 
- 1. 
    - ctrl+r调出标尺, 或者视图菜单选择标尺
    - 标尺单位改成像素
    - ctrl+=/ctrl+-放大缩小
    - 按空格抓手模式
    - 选取工具在左竖栏

## 其它随笔
- 1. `list-style: none`去掉无序列表前边的小圆点

## 圆角边框/盒子阴影/文字阴影(09-css3_new.html)
- 1. 圆角边框
    - `border-radius`
    - 设置圆角/设置椭圆角
- 2. 盒子阴影
    - `box-shadow`
    - 盒子阴影不占空间, 不影响其它网页元素
- 3. 文字阴影
    - `text-shadow`

## 浮动(10-float.html)
- 1. 传统网页布局的三种方式
    - css放盒子: 普通流(标准流 文档流), 默认排列/浮动/定位
    - 实际开发之中这三种布局方式都会经常用到
    - 纵向排列标准流, 横向排列用浮动
- 2. 浮动
    - `float`, 值可以是`left`/`right`/`center`
    - 浮动元素会脱离标准流(脱标)
    - 浮动元素上边缘对齐
    - 若宽度太小, 浮动元素会往下排列
    - 行内元素转浮动, 可以给宽度和高度
    - 块级元素添加浮动后, 默认宽度根据内容决定
    - 一般浮动的用法是先用父级元素标准流纵向排列, 再用浮动子元素横向排列
    - 浮动的元素会影响其之后的标准流, 不会影响之前的标准流
    - 
- 3. 常见网页布局
- 4. 清除浮动: 
    - 需求在于使父盒子大小根据子盒子大小调整
    - 方法有多种
    - 方法一: 额外标签法: 新建一个子元素, 设置样式: `clear: both;`, 新增的子元素只能是块级元素
    - 方法二: 父元素添加样式: `overflow`
    - 方法三: `:after`伪元素法    
    - 方法四: 双伪元素法

## PS切图
- 1. png支持背景透明/PSD设计稿
- 2. ps切图针对PSD文件
- 3. cutterman 最好用的切图工具, ps的插件

## 定位
- 1. 为什么需要定位? 什么是定位?
    - 盒子覆盖?
    - 定位是固定位置?
    - 定位=定位模式+边偏移
- 2. 定位
    - 定位模式: `static`/`relative`/`absolute`/`fixed`
    - `static`为默认定位, 无定位, 没有脱离标准流, 不常用
    - `relative`非常重要, 相对于自己以前的定位移动, 相对定位不影响标准流(不脱标)(不是很影响)
    - `absolute`非常重要, 相对于祖级元素移动, 如果没有祖先元素或者祖先元素没有定位, 按文档偏移; 如果有祖先定位, 按最近一级祖先的定位偏移. 绝对定位是脱标的
    - 口诀: 子绝父相
    - `fixed`重要, 以浏览器的可视窗口为基准偏移, 固定定位脱离标准流
    - `fixed`与版心对齐(而不是与浏览器边框对齐)的方法: 如`left: 50%`
    - `sticky`粘性定位, 移动之后, 到达一定位置就固定了. 兼容性不好, 用得少
    - `z-index`设置元素叠放次序, 如果`z-index`值相同, 按元素的书写顺序排列, 只有定位的盒子才有这个属性
    - 绝对定位的盒子(`absolute`)不能用`margin auto`的方法居中, 用: `left: 50%; margin-left: 自己盒子的一半`
    - 行内元素添加绝对或者固定定位, 可以直接设置宽高
    - 块级元素添加绝对或者固定定位, 默认由内容撑起大小
    - 脱离标准流的元素不会触发外边距合并
    - 一般浮动元素会环绕标准流中的文字, 但脱标的元素会压住标准流中的文字

## 元素的显示与隐藏
- 1. `display`(用的多)
    -`display: none;`隐藏元素, 同时元素的占用空间消失
    -`display: block;`是`display: none;`的反属性
- 2. `visibility`(用的少)
    -`display: hidden;`隐藏元素, 但元素的占用空间保留
- 3. `overflow`
    -`overflow: hidden;`隐藏溢出元素
    -`overflow: scroll;`隐藏溢出元素, 添加滚动条
    -`overflow: auto;`隐藏溢出元素, 按需添加滚动条
    - 定位元素慎用`overflow`
