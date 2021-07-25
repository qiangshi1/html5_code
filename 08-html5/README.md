# h5(html5)新特性

## 语义强化标签
- 1. `<header>`/`<nav>`/`<article>`/`<section>`/`<aside>`/`<footer>`
    - 这些标签针对搜索引擎的, 对于前端开发人员和`<div>`一模一样

## 多媒体标签
- 1. `<video>`
    - mp4的浏览器兼容性最好, 推荐用mp4格式的视频文件.
    - 下边代码片段的意思是: 若能够播放movie.mp4, 就播放movie.mp4; 否则, 播放movie.ogg. 相当于条件判断功能, 为了照顾浏览器兼容性. 参考: https://www.runoob.com/html/html5-video.html
        ```html
        <video width="320" height="240" controls>
            <source src="movie.mp4" type="video/mp4">
            <source src="movie.ogg" type="video/ogg">
            <!-- 您的浏览器不支持Video标签。 -->
        </video>
        ```
- 2. `<audio>`
    - 对mp3支持性最好

## input新增
- 1. `type`
    - `type="email/url/date/time/month/week/number/tel/search/color"`
    - 重点记住`number/tel/search`
- 2. 新增属性
    - `required/placeholder(autofocus: placeholder的属性)/autocomplate/multiple`
    - 设置`input`的`placeholder`样式的css写法:
    
        ```css
        input::placeholder {
            color: pink;
        }
        ```
    - 重点是`placeholder/multiple`