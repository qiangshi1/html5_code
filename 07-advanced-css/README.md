# css高级技巧

## 精灵图
- 1. 为了节省向服务器请求图片的次数(小而多的图片集合)
    - 借助属性: `background-position`
    - `background-position:`得放在`background: url()`下面, `background-position: 0 -219px;`表示想左移动0px, 向下移动-219px

- 2. 字体图标(展示的的是文字, 本质是图片)
    - 字体图标的下载: http://icomoon.io/app http://iconfont.cn, 得到icomoon.zip(以在http://icomoon.io/app中下载为例)
    - 把fonts目录放在根目录下
    - style标签中字体声明(style.css中的第一个json段落, style.css在下载的icomoon.zip下)
- 3. 三角形状
    - 用border做
- 4. 样式
    - 鼠标样式: 放在元素上的样子
    - 禁止出现表单轮廓线
    - 禁止调整文本域大小, 禁止出现文本域轮廓线(方法同禁止出现表达轮廓线)
- 5. 实现图片和文字垂直居中
    - `vertical-align`: 只针对行内块元素
    - 文本四条线: 顶线(top line)/中线(middle line)/基线(base line)/底线(bottom line)
    - 如`vertical-align: center;`使图片和文本中线对齐, 注意`vertical-align: center;`是前面图片的属性
    - img图片底部存在缝隙问题, 解决方法: 1: 添加`vertical-align`, 只要不是基线对齐就行; 2: 图片转成块级元素: `diplay: block;`
- 6. 溢出文本
    - 单行: `white-space: nowrap;`文本取消多行, `text-overflow: ellipsis;`添加省略号
    - 多行: 用到了webkit, 但兼容性差.
        ```html
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 3;  /*第几行省略*/
        -webkit-box-orient: vertical;
        ```
    -  多行推荐在后台做

- 7. 布局技巧(07-layout-skills.html)
    - `margin`负值: 防止border变粗, 但是缩放110% 125%还是会看到不同的盒子边框粗细不同; 边框变换形式要用相对定位以压住其他盒子; 如果还不行, 加`z-index`
    - 文字围绕浮动元素: 浮动的本来作用
    - 行内快元素的巧妙运用: 居中`text-align: center`
    - 三角形(另一个三角形)

- 8. css初始化
    - 为保证浏览器兼容性, 必须初始化css




