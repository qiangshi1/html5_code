# 移动端基础

## 导读
1. 移动端浏览器基本上都是基于webkit内核的
2. 移动端要考虑屏幕尺寸多的问题
3. PC端浏览器基本上都有模拟移动端的功能----按f12打开调试

## 视口
1. 浏览器显示的屏幕区域, 分为布局视口/视觉视口/理想视口
2. 布局视口
3. 视觉视口
4. 理想视口
5. meta视口标签
    - 用理想视口显示, 就是这个东西:
    ```html
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```
    - 上边的例子content中还有其他的东西

## 物理像素和实际像素
1. 物理像素是真实存在的
    - 但开发中1px并不一定等于1个物理像素
2. 移动端物理像素与实际像素并不一定一一对应
    - 移动端会有一个映射比
    - 开发尺寸(PC端浏览器模拟移动端)是实际像素

## 二倍图
1. 我们准备的图片的大小是实际用的图片的二倍.
2. 当然还有三倍图/四倍图的情况

## 背景缩放(background-size)
1. cover和contian可以覆盖
    - 但cover可能会有内容缺失
    - contain可能会有图片形变的问题
    - ps切出二倍图

## 移动端开发准备
1. 单独制作移动端页面
    - 主流是单独制作一个移动端页面, 由浏览器标识切换, 主流
    - 还有响应式页面, 三星手机官网的做法, 非主流
    - 域名前面加上m
2. 移动端css初始化
    - 
3. 盒子模型
    - padding和border不会撑大盒子
4. 移动端特殊样式
    - `-webkit-tap-highlight-color: transparent;`取消a链接选中高亮
    - `-webkit-appearance: none;`取消input边框凸出效果
    - `-webkit-touch-callout: none;`禁止长按弹出菜单
5. 布局
    - 流式布局/flex布局/rem适配布局
6. 第1种布局模式: 流式布局
    - 就是百分比布局
    - 如:`width: 50%;`这种写法, 单位是百分比
    - 避免无限缩放, 再设置`max-width`/`min-width`
7. 第2种布局模式: flex布局(弹性布局)
    - 传统的布局很繁琐, flex布局更简单, 但兼容性差, 主要不支持IE, 移动端的兼容性是没问题的
    - PC端还是传统布局, 移动端推荐flex布局
    - 任何一个容器都可以指定为flex布局
    - 当父元素指定为flex布局时, 子元素的float(浮动) clear(清除浮动) vertical-align属性均失效
    - 采用flex布局的元素称为flex容器, 容器中的成员成为项目
    - 子容器可以横向排列也可以纵向排列
    - 通过给父盒子添加flex, 以控制子盒子的位置和排列方式
    - flex父盒子常见属性: flex-direciton/juesity-content/flex-wrap/align-items/align-content/flex-flow
    - flex-direciton定义主轴. 主轴: 默认水平向右, 侧轴: 默认垂直向下. 可以通过flex-direciton设置, 默认是`flex-direction: row;`
    - juesity-content设置主轴上的子元素排列方式. flex-start(默认)左对齐/flex-end右对齐/center居中对齐/space-around平分剩余空间/space-between(重要)先两边贴边, 再平分剩余. 
    - flex默认会让子元素硬挤在一行显示, 即有时会缩小子元素
    - flex-wrap换行: no-wrap(默认)不换行/wrap换行
    - align-items设置侧轴上的子元素排列方式, 单行的时候使用. flex-start(默认)左对齐/flex-end右对齐/center居中对齐/stretch拉伸(子盒子不要给高度) 
    - align-content设置侧轴上的子元素排列方式, 多行的时候使用(单行无效). flex-start(默认)左对齐/flex-end右对齐/center居中对齐/space-around平分剩余空间/space-between先两边贴边, 再平分剩余/stretch拉伸(子盒子不要给高度).
    - flex-flow简写写法, 简写flex-direciton和flex-wrap的, 如: `flex-flow: flex-direciton flex-wrap`
    - flex子盒子常见属性: flex/align-self/order
    - flex(重要)定义子盒子分配剩余空间, 用flex表示占用的份数(也可以理解为权重).
    - align-self定义子盒子侧轴排列方式, 给每个子盒子设置可以使各个子盒子的状态不相同
    - order定义子盒子的顺序, 比如共有三个子盒子1 2 3, 如果给3号盒子设置`order: -1;`, 盒子的排列状态是3 1 2. 
8. 第3种布局模式: rem适配布局(04-rem.html 05-less.html)
    - 优点: 字体大小随屏幕大小变化而变化
    - em单位: 相对于父元素的字体大小的倍数
    - rem(root em)单位: 相对于html字体大小的倍数(rem可以看做一种特殊的em)
    - 媒体查询: 可以根据不同的屏幕尺寸改变样式:
        ```css
        /* 屏幕上, 并且最大宽度800px */
        @media screen and (max-width: 800px) {
            .box3 {
                background-color: pink;
            }
        }
        /* 后边覆盖前边的 */
        @media screen and (max-width: 500px) {
            .box3 {
                background-color: cornflowerblue;
            }
        }
        ```
    - 媒体查询的引入资源(理解): 
        ```css
        /* 根据媒体查询引入不同的css文件 */
        <link ref="stylesheet" href="style320.css" media="screen and (min-width: 320px)">
        <link ref="stylesheet" href="style640.css" media="screen and (min-width: 640px)">
        ```
    - less(leaner style sheets), 对标css, 中文官网: www.lesscss.cn
    - less变量. 写法: `@var: value;` 注意@开头, 大小写敏感. 用的时候用直接用`@var`, 如: `div {color: @var}` 
    - vscode less插件: easyless. less文件转css, 创建less文件每次保存生成新的css文件. 
    - less嵌套: 
        ```less
        body {
            font-size: @basefont;
            background-color: @basecolor;
            .header {
                color: red;
            }
        }
        ```
    - less伪类: `&:hover{}`
    - less伪元素: `&::before`
    - less伪类/伪元素/交集选择器前都要加&符号
    - less运算. 支持一些值的加减乘除运算. 运算符左右空格隔开, 如: `@baseborder: 5px - 2;`. 两个数的运算, 第二个数没有单位, 继承第一个数的单位; 两个数的运算, 第二个数有单位, 结果单位是第一个数的单位. 颜色也可以参与运算, 如: `#222 - #444`
    - rem适配布局技术方案1: rem+媒体查询+less; rem适配布局技术方案2: flexible.js+rem. 两个方案都常见




















