# day5

#### Bootstrap

*   快速入门

    *   下载bootstrap

    *   在项目中将这三个文件夹复制

    *   创建html页面，引入必要的资源文件

        ```
        <!DOCTYPE html>
        <html lang="zh-CN">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
            <title>Bootstrap HelloWorld!</title>
        
            <!-- Bootstrap -->
            <link href="css/bootstrap.min.css" rel="stylesheet">
        
            <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
            <script src="js/jquery-3.6.0.min.js"></script>
            <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
            <script src="js/bootstrap.min.js"></script>
        
        </head>
        <body>
        <h1>Hello World!</h1>
        
        
        </body>
        </html>
        ```

*   响应式布局

    同一套页面可以兼容不同分辨率的设备

    *   实现：依赖于栅格系统（将一行平均分为12个格子，可以指定元素占几个格子）
    *   步骤：
        1.  定义容器。相当于之前的table
            *   容器分类：
                *   container：
                *   container-fluid：每一种设备都是100%宽度（没有留白部分）
            
        2.  定义行。相当于之前的tr （样式：row）
        
        3.  定义元素。相当于td。指定该元素在不同的设备上所占的格子数目。 （样式：col-设备代号-格子数目）
            *   设备代号
                *   xs：.col-xs-12
                *   sm
                *   md
                *   lg
            
        4.  注意：
        
            一行中如果格子数目超过12，则超出部分自动换行
        
            栅格类属性可以向上兼容。栅格类适用于与屏幕宽度大于或者等于分界点大小的设备
        
            如果真实设备宽度小于了设置栅格类属性的设备代码的最小值，会一个元素占满一整行

*   CSS样式和JS插件

    *   全局css样式：更多请具体参看Bootstrap文档

        *   按钮

            ```html
            <button type="button" class="btn btn-default">（默认样式）Default</button>
            ```

        *   图片

            ```html
            <img src="..." class="img-responsive" alt="Responsive image">
            ```

            图片在任意尺寸都占100%

            ```html
            <img src="..." alt="..." class="img-rounded">
            <img src="..." alt="..." class="img-circle">
            <img src="..." alt="..." class="img-thumbnail">
            ```

            图片形状也可以改变，方的、圆的、边框形

        *   表格

            ```
            <table class="table table-bordered table-hover">
            ```

        *   表单

            给表单项添加 class="form-control" 

    *   组件：更多请具体参看Bootstrap文档

        *   导航条
        *   分页条

    *   插件：更多请具体参看Bootstrap文档

        *   轮播图

