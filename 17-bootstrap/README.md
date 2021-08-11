# bootstrap框架

## 
1. `<header>`标签中, `<meta http-equiv="X-UA-Compatible" content="IE=edge">`的意思是使用IE的最高版本内核来渲染
2. 条件注释写法: 
```html
    <!--[if lt IE 9]>
        <script src="https://cdn.jsdelivr.net/npm/html5shiv@3.7.3/dist/html5shiv.min.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/respond.js@1.4.2/dest/respond.min.js"></script>
    <![endif]-->
```
3. 新增类名来修改bootstrap的样式(覆盖原来的样式)
4. boostrap的container类就是响应式布局, 如12-base-mobile/06-responsive-layout.html的布局
5. container是一种预定义类

## boostrap栅格系统
1. 栅格系统. gridsystems, 又称格子系统
    - 基本: `col-xx-number`, xx=`xs/sm/md/lg`
2. 最多划分为12列
3. 可能和margin冲突, 处理方法, 里边套一个盒子
4. 列嵌套
5. 列偏移
    - `col-md-offset-8`
6. 列排序, 元素可以交换位置
    ```html
        <!-- 列排序 -->
        <div class="row">
            <!-- 向右是push, 向左是pull -->
            <div class="col-md-4 col-md-push-8">left</div>
            <div class="col-md-8 col-md-pull-4">right</div>
        </div>
    ```
7.  元素的显示与隐藏
    - 根据屏幕宽度隐藏: `hidden`
    - 根据屏幕宽度显示: `visible`










