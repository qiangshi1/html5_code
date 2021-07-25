# 杂项----老师在p353-p389之间讲的内容

## 2D转换
1. translate 三种写法: `transform: translate(100px, 200px);`/`transform: translateX(100px);`/`transform: translateY(100px);`(01-translate.html)
    - 注意这3种写法效果不叠加, 最后一个生效
    - 这个和相对定位有什么区别?
    - 可以使用百分比单位, 百分比单位是相对于自身元素的translate
    - 对行内标签没有作用
    - translate可以替换掉margin实现居中的效果(`transform: translate(-50%, -50%);`)
2. rotate (2D旋转)写法: `transform: rotate(50deg);`(02-rotate.html)
    - 正为顺时针旋转
    - 设置旋转中心: `transform-origin: 50% 50%;`
3. scale (2D缩放)写法: `transform: scale(x, y);`(03-scale.html)
    - x, y不跟单位, 表示原来长宽的倍数
    - 设置缩放中心: `transform-origin: right bottom;`
4. translate rotate scale 连写, 写法: transform: translate() rotate() scale() ...;
    - 其顺序会影响转换效果
    - 位移要放在最前

## animation(相比于过渡, animation可以实现更多的控制更多的效果)
1. animation写在css中, 
    - 关键步骤包括: 定义关键帧(开始状态/结束状态)/执行/执行时间, 一个demo:
    ```css
    /* 定义关键帧 */
    @keyframes move {
        /* 开始状态 */
        0% {
            transform: translateX(0px);
        }
        /* 结束状态 */
        100% {
            transform: translateX(500px);
        }
    }
    .box1 {
        width: 200px;
        height: 200px;
        background-color: pink;
        /* 执行 */
        animation: move;
        /* 执行时间 */
        animation-duration: 1s;
    }
    ```
    - 0%又可以写成from, 100%又可以写成to
    - 关键帧可以有多帧, 即并不只包含开始状态/结束状态
    - 常用属性: `animation-name`/`nimation-duration(值可以是ns或者nms)`/`animation-timing-function(速度曲线)`/`animation-delay(延迟执行)`/`animation-iteration-count(重复次数, 可以是数字或者infinite(无限))`/`animation-direction(下一周期是否逆向)`/`animation-fill-mode(结束时的状态, 返回起始还是保持终点)`/`animation-play-state(暂停动画用paused, 一般用条件控制)`
    - `animation-timing-function` 动画的配速曲线, 可以设置多种值, https://www.runoob.com/cssref/css3-pr-animation-timing-function.html
    - animation的一种简写形式: `animation: name duration timing-function delay iteration-count direction fill-mode`
    - `animation-timing-function` 写steps动作可以变成离散的. 
    - 一个元素可以添加多个动画: 写法如: `animation: moving_bear 0.5s steps(8) infinite, running_bear 5s linear;`, 注意逗号隔开. 
## 3D旋转
1. 三维坐标系
    - x向右, y向下, z向屏幕外边
2. 3D位移 `translateZ(npx)`
    - 简写方法: `translate3d(x, y, z)`, x, y, z不能省略(可以写0)
    - 旋转的正负满足左手准则
3. perspective 透视
    - 近大远小
    - 透视写在被观察元素的父盒子处
4. transform-style(重要)
    - 开启立体空间 `transform-style: preserve-3d;`
    - 
## 浏览器私有前缀
1. 
    - 为了兼容老版本浏览器
    - `-moz-`(firefox)/`-ms-`(ie)/`-webkit-`(safari/chrome)/`-o-`(opera)
    - 一种写法: `-moz-border-radius: 10px`
    - 先写浏览器私有属性, 再写通用属性

## 以上时PC端




