# 品优购项目

## 目录划分
1. css 样式文件夹
2. images 图片
3. js 脚本
4. upload 经常更换的图片
5. index.html 主html
6. fonts 字体文件

## css
1. base.css
    - 全局样式
2. common.css
    - 各个网页可以复用的样式

## 网站图标 favicon
1. 必须是后缀为.ico的文件, 可以通过网站bitbug.net把一张普通的图片转成.ico文件
2. 需放在网站根目录下
3. `<link rel="shortcut icon" href=" /favicon.ico" />`在`<head>`中引入
4. 大部分网站找图标的方法: 如https://www.baidu.com/favicon.ico

## SEO 搜索引擎优化
1. 对网站优化, 提升搜索引擎曝光率
2. title
    - 写成网站名(产品名)-网站介绍(尽量不超过30个汉字)
3. description
    - `<meta name="description" content="巴拉巴拉"/>`
4. keywords(重要的关键字靠前)
    - `<meta name="keywords" content="巴拉巴拉" />`
5. logo SEO优化
    - logo中放一个`<h1>`标签
    - `<h1>`放一个链接, 返回主页
    - 链接中要放文字
    - 链接放一个`title`属性, 鼠标放在上边会有提示信息
    - 具体写法为: 
    ```html
    <div class="logo">
        <h1>
            <a href="index.html" title="品优购商城">品优购商城</a>
        </h1>
    </div>
    ```
    - 其中title是鼠标放上去之后出现的提示, 注意在写超链接的样式是要转成块级元素, 显示的图片是背景图片

## search搜索模块

## 按钮模块
1. `border-radius: 7px 7px 7px 0px;`3个圆角1个直角

## 注册页面
1. 基于隐私的考量, 注册页面不需要SEO优化


