# html相关

## 什么是html(01-html.html)
- 1. html是超文本标记语言. 
- 2. 01-html.html是一个简单的demo. 

## 常用浏览器
- 1. 浏览器内核. 

## web标准
- 1. 为什么要有web标准?
- 2. 有哪些web标准? 
    - 结构/表现(主要指css)/行为(主要是JavaScript). 

## html的标签(02-first_html.html)
- 1. html语法规范
    - 所有的标签都要有尖括号包裹, 标签一般成对出现, 但是也有单标签.
    - 结束标签有反斜杠. 
    - 标签(之间)的关系: 包含和并列. 
- 2. html基本结构标签
    - `<html>`是根标签
    - `<head>`是头标签
    - `<title>`是标签标签
    - `<body>`是主体标签

## 在vscode中创建html(03-vscode_html.html)
- 1. 用`!`可以快速创建一个页面的框架.
- 2. 推荐插件:
    - open in browser
    - auto rename tag
    - css peek
    - live server[自推荐]

## 在vscode中用`!`创建的html的部分标签(03-vscode_html.html)
- 1. `<!DOCTYPE html>` 表示指定html5, 必须写在第一行.
- 2. `<html lang="en">` 表示当前网页是一个英语网页, 但是可以在英语网页中可以显示中文. 对浏览器和搜索引擎有作用. 推荐该标签为: `<html lang="zh-CN">`
- 3. `<meta charset="UTF-8">`指定文本编码 这句话一定要写. `UTF-8`又被称为万国码, 通常用这个. 
- 4. 其他几个标签随后再介绍

## 常见标签(04-common_tags.html)
- 1. 标题标签: `<h1>`~`<h6>`
    - 标题标签字体更加显眼
    - 标题标签独占一行

- 2. 段落标签: <p>
    - 网页中多个空格连续只显示一个
- 3. 强制换行: `<br>`
    - `<br>`是单标签
- 4. 文本的粗体`<strong>` `<b>`/斜体`<em>` `<i>`/下划线`<ins>` `<u>`/删除线`<del>` `<s>`效果
    - 
- 5. 无语义标签
    - `<div>`
    - `<span>`
- 6. 图像标签`<img>`
    - src属性是图像路径
    - alt属性是替换文本, 图片不能正常显示是显示该文本
    - title属性是鼠标放在图片上的提示文体
    - width给图像设置宽度
    - heght给图像设置高度, heght和width同时设置可能会造成图像形变, 一般只设置一个. 
    - border边框
    - 属性之间没有顺序, 用空格分隔, 键="值"格式
- 7. 超链接标签`<a href>`
    - 分为外部链接/内部链接/空链接/下载链接/锚点链接
    - 属性`target`表示打开方法, 有`_self`和`_blank`两个值
- 8. 表格标签`<table>`/`<tr>`/`<td>`
    - 基本用法
    - `<th>`标签: 表头, 居中且粗体
    - 表格的相关属性: align(left center right), 单元格位置放置方式/border(1或者""), 边框/cellpadding(像素值), 单元格与内容之间的空白/cellspacing(像素值), 单元格与单元格之间的空白/width, 宽度/height, 高度
    - 单元格里可以放任意元素
    - `<thead>`/`<tbody>`使表格结构更加清晰. 注意`<thead>`/`<tbody>`和`<th>`/`<td>`不是一回事
    - 合并单元格, `colspan`(行合并)/`rowspan`(行合并)
- 9. 列表标签`<table>`/`<tr>`/`<td>`
    - 分为无序列表/有序列表/自定义列表
    - 无序列表`<ul>`是没有顺序的, `<ul>`中只能嵌套`<li>`, `<li>`中可以放许多元素. 
    - 有序列表`<ol>`
    - 自定义列表`<dl>`
- 10. 表单标签
    - 出现标签: `<form>`/`<input>`
    - `<input>`的type属性有很多的值
    - `<label>`标签可以扩展选中域
- 11. 下拉标签`<select>`
    - 子标签`<option>`
- 12. 文本域标签`<textarea>`
    - 不同于`<input>`, `<textarea>`支持多行

## 特殊
- 1. `<!--  -->`注释语句, 给程序员看的, 并不执行. 
- 2. 转义字符 https://tool.oschina.net/commons?type=2

## 文档
- 1. https://www.w3school.com.cn/
- 2. 等等