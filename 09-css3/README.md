# css3新增

## 选择器
1. 属性选择器`[xxxx]`
    - 根据元素属性选择
    - 基本写法:
        ```css
        input[value] {
            color: pink;
        }
        ```
    -进阶: `[attribute=xxx](同[attribute="xxx"])`选择属性值(重点); `[attribute=^xxx]`选择以xxx为开头的属性值; `[attribute=xxx$]`选择以xxx为结尾的属性值(重点); `[attribute*="xxx"](注意有引号)`选择有xxx的属性值(重点)
    - 类选择器/属性选择器/伪类选择器权重都是10
2. 结构伪类选择器(`:`形式上十分接近伪类选择器)
    - `first-child/last-child/nth-child(number)(重要)`
    - `nth-child()`支持数字/even(偶数)/odd(奇数)/n(选中所有, n从0开始自增)/3n(选中3的倍数), 即支持简单的数学表达式
    - `first-of-type/last-of-type/nth-of-type(n)`与`-child`类似, 但有如下区别: `-child`先选择序号, 再看类型; `-of-type`先看类型, 再看序号
3. 伪元素选择器
    - 所谓伪元素, 是用css写的元素, 伪元素在文档树中是不存在的
    - `::before`/`::after`, 创建的元素是行内元素, `::before`在父元素之前创建一个元素, `::after`在父元素之后创建一个元素
    - 之前清除浮动用的就是这个东西
    - `::before`/`::after`中必须要有`content`
    - 伪元素选择器和条件判断选择器的一个混合写法例子:
        ```css
        .box2:hover::after
        ```
    - `display: table`

## css3盒子模型border-box
1. `box-sizing: border-box;`表示`border`/`padding`不会撑大盒子

## css3的其它新特性
1. `filter` 元素模糊或元素偏移
    - `filter: blur(5px)`: 图像模糊
2. `calc`一些计算
    - 支持 +, -, *, / 运算；
3. css3过渡(动画效果)(重点)
    - `transition`: 要过渡的属性 花费的时间 运动曲线 何时开始
    - 多个过渡动画写法: `transition: width .5s ease 0.2s,  height .5s ease 0.2s;`
    - 多个过度动画简写写法: `transition: all .5s ease 0.2s`

## 广义的HTML5=狭义的html5+css3+js