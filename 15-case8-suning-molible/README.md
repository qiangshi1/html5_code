# 苏宁易购客户端----rem适配布局

## rem适配布局技术方案2: flexible.js+rem

## flexible.js是开源项目, 地址在:
1. 用flexible.js之后无需再写媒体查询
2. flexible.js在https://github.com/amfe/lib-flexible目录下, 和老师讲的不一样, 我的是index.js. 
3. flexible.js下10rem是当前html的宽度. 1rem是html的font-size, 所以flexible.js可以根据页面宽度修改字体大小. 

## vscode插件cssrem
1. vscode插件cssrem, px转rem的工具. 是在代码补全处. 
    - settings.json中修改px到rem的比值: `"cssrem.rootFontSize": 16`. 

## 杂项
1. css增加权重: `font-size: 75px!important;`
2. 还是不可避免地要用到媒体查询吗?
    ```css
        /* 如果屏幕超过了750px, 还是使用媒体查询? */
        @media screen and (min-width: 750px){
        html {
            font-size: 75px!important;
        }
        
        }
    ```

## 小结
1. 老师只做了顶部搜索框部分, 剩余的部分没有做
2. 老师更推荐这种方案






