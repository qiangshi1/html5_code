# 京东移动端案例
1. normalize.css
    - 地址: https://github.com/necolas/normalize.css
    - 它的星星还挺多

2. 图片无法居中时, 注意是不是没有加`vertical-align: middle;`

3. 精灵图的缩放----以二倍精灵图为例
    - 精灵图(xx.png)缩小二分之一测量位移x, y
    - 设精灵图宽度的二分之一是l
    - 写代码: 
    ```css
    background: url(xx.png) no-repeat xpx ypx;
    background-size: lpx auto;
    ```

4. dpg是京东出的一种图片格式, 有损压缩, 但占用空间小
    - 我就用jpg了

5. 固定定位(fixed)脱离标准流

6. 默认图片底部会有空白缝隙, 用`vertical-align: top;`去除

7. rem单位, 先跳过去, 以后再学

8. webp格式, 类似于dpg, 但是谷歌开发的
    - 我就用png了

9. 京东快报, 等学了js后再做



