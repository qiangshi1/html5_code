# 携程移动端----应用flex布局

##
1. 图片素材摘自https://github.com/webximi/xiecheng

## 注意点
1. 固定定位下`margin 0 auto`无效
2. 二倍精灵图: 先缩后量
3. c3盒子模型的line-height要想文本居中应该为height-2*border
4. margin给负值的作用
5. 精灵图只能用作背景, 而不能用作img元素? 
6. 图片名称中有@2x, 表示它是二倍精灵图
7. hotel.png是一个三倍图
8. 渐变背景色
    - 线性渐变:
        ```css
        /* left是起始方向 */
        background: -webkit-linear-gradient(left, red, blue);
        /* 左上角是起始方向 */
        background: -webkit-linear-gradient(top, left, red, blue);
        ```
9. flex除了可以写整数之外还可以写百分比, 如: `flex: 20%;`


