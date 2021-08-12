# 黑马面面项目

## 准备工作
1. 现如今切图不用前端来做了, 由美工来做, 通过蓝湖或者募客. 
    - 蓝湖和募客是一个团队协作平台. 
    - 募客官网: https://www.mockplus.cn/. 
    - 在募客上下载ps插件
    - 募客可以看做一个云端的切图服务, 募客还挺强大的. 
    
## 制作
1. 单纯写代码你会发现你的元素比老师演示的大很多, 原因在于老师的flexible.js的1rem=屏幕宽度/20, 修改方法为: 在js/index.js中: 
    ```js
    // set 1rem = viewWidth / 10
    function setRemUnit () {
    var rem = docEl.clientWidth / 20 //10改成20
    docEl.style.fontSize = rem + 'px'
    }
    ```
2. 为什么我的图片必须加`width: 100%;`, 否则会太大? 
3. swipper轮播图开源项目
    - 官网: https://www.swiper.com.cn/
    - 老师的版本: swiper-5.4.5.zip
    - 关键文件: swiper.min.css/swiper.min.js, 分别放在css和js目录下
    - 用法: 官网下载demo, 然后进行小修, demo引入方法:
    ```html
        <!-- Swiper -->
        <div class="swiper-container">
            <div class="swiper-wrapper">
            <div class="swiper-slide">Slide 1</div>
            <div class="swiper-slide">Slide 2</div>
            <div class="swiper-slide">Slide 3</div>
            <div class="swiper-slide">Slide 4</div>
            <div class="swiper-slide">Slide 5</div>
            <div class="swiper-slide">Slide 6</div>
            <div class="swiper-slide">Slide 7</div>
            <div class="swiper-slide">Slide 8</div>
            <div class="swiper-slide">Slide 9</div>
            <div class="swiper-slide">Slide 10</div>
            </div>
            <!-- Add Pagination -->
            <div class="swiper-pagination"></div>
        </div>
    ```
    和css代码:
    ```less
        .swiper-container {
        width: 100%;
        height: 100%;
        }
        .swiper-slide {
        text-align: center;
        font-size: 18px;
        background: #fff;

        /* Center slide text vertically */
        display: -webkit-box;
        display: -ms-flexbox;
        display: -webkit-flex;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        -webkit-justify-content: center;
        justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
        -webkit-align-items: center;
        align-items: center;
        transition: 300ms;
        transform: scale(0.8);
        }
        .swiper-slide-active,.swiper-slide-duplicate-active{
        transform: scale(1);
        }
    ```
    和js代码(html中, 以script方式引入): 
    ```html
        <!-- Initialize Swiper -->
        <script>
            var swiper = new Swiper('.swiper-container', {
            slidesPerView: 3,
            spaceBetween: 30,
            centeredSlides: true,
            loop: true,
            pagination: {
                el: '.swiper-pagination',
                clickable: true,
            },
            });
        </script>
    ```
    - 记得要引入swiper.min.css和swiper.min.js哦.
    - 在`<swiper>`中引入swiper要闭包, 防止用多个swiper时swiper之间相互冲突
    - 用opacity修改透明度
    -  `.swiper-slide-active, swiper-slide-duplicate-active`是当前选中的slide, 也就是中间的那个
    - `z-index`修改元素的覆盖关系
    - `.swiper-button-next, .swiper-button-prev`定义在`<script>`中, 如下: 
    ```js
        // 添加左右箭头
        navigation: {
            nextEl: ".swiper-button-next",
            prevEl: ".swiper-button-prev",
        },
    ```
    - swiper显示的个数可以是小数
    - ` slidesPerView: 3`要从3改成2, 表示当前轮播图最多显示个数, 

## 把代码提交到码云, 未做
1. 代码上传
2. 静态网页预览