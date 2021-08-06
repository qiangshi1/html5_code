# 苏宁易购客户端----rem适配布局

## rem适配布局技术方案1: rem+媒体查询+less

## common.less
1. 公共less
2. PC段默认html字体50px
3. 在less文件中引入less文件, 如:
    ```less
    @import "common";
    ```
4. 关于easyless插件, 加上括号才会编译成功, 不加括号可能有问题, 但老师演示得没有问题. 如`font-size: (320px / @no)`

## index.less
1. `margin: 0 auto`要想居中必须给定宽度
2. 广告部分图片(upload/ad1.gif upload/ad2.gif upload/ad3.gif)可能显示不出来的原因是浏览器插件adblock