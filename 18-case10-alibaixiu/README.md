# 阿里百秀项目----应用boostrap

## 制作: 
1. container宽度的修改
```css
    @media screen and (min-width: 1280px) {
        .container {
            width: 1280px;
        }
    }
```
2. boostrap的row自带pading, 考虑去除
3. css优先级
4. boostrap的字体图标
    - 第一步: 在官网上找到你想要的字体图标的名字(https://v3.bootcss.com/components/), 如`glyphicon glyphicon-camera`
    - 第二步: class引入: `<a href="#" class="glyphicon glyphicon-camera">生活馆</a>`
    - 第三步: 做一点适配
5. a嵌套img的问题: https://blog.csdn.net/weixin_39666697/article/details/78846406
6. boostrap自带清除浮动, 用法: `class="clearfix"`
7. boostrap还内置了许多其他的样式. 
8. 这里小屏下logo图片为什么会居中?
```css
    .logo img {
        display: block;
        /* width: 100%; */
        /* logo图片不需要缩放 */
        max-width: 100%;
        margin: 0 auto;
    }
```

## 响应式布局不同屏幕宽度下各个元素的变化
1. logo的变化
    - 图片 文字 互转(其实就是两个元素在不同屏幕下的显示和隐藏)
    - 有机会好好理解下`max-width: 100%;`
2. nav的变化
    - 除了样式的变化还有文字大小的变化
3. news的变化
    - 5个块, 第1个块在左边和上边的切换
4. publish的变化
    - 元素的显示和隐藏
    - h3文字的大小变化

## 小结
1. 这里的页面和老师的略有区别, 但大同小异. 主要原因是老师的一些素材我没有找到
2. 单纯用boostrap无法完成所有的响应式功能, 可能还要辅以媒体查询
3. 这里演示的是响应式布局, 实际开发中更多的还是flex弹性布局和rem适配布局
