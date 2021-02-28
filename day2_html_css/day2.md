# Day2

## HTML&CSS

### HTML表单标签

*   form 用于定义表单。可以定义一个范围，范围代表采集用户数据的范围。
    用form把想要提交数据的对象全部包裹起来
    action: 指定提交数据的URL
    method:分类：一共七种，两种比较常用
    	get：
    		1.请求参数会在地址栏中显示，会封装在请求行中（HTTP）
    		2.请求参数的长度有限制
    		3.不太安全
    	post：
    		1.请求参数不会在地址栏中显示，会封装在请求体中（HTTP）

​		2.请求参数的长度没有限制
​		3.比较安全

*   表单项中的数据要想被提交，必须指定其name属性

*   表单项标签：

    *   input：可以通过tpye属性值，改变元素展示的样式

        *   label：指定输入的文字描述信息

            *   注意：
                *   label的for属性一般会和input的id属性值对应，如果对应了，则点击label区域，会让input输入框获取焦点。

        *   tpye属性：

            *   text：文本输入框，默认值
                *   placeholder：指定输入框的提示信息，当输入框的内容发生变化，它自动清空
            *   password：密码输入框
            *   radio：单选框
                *   注意：
                    *   要让多个单选框实现单选的效果，则多个单选框的name属性必须一样
                    *   一般会给每个单选框提供value属性，指定其被选中后提交的值
                    *   checked属性，可以指定默认值
            *   checkbox：复选框
                *   注意：
                    *   一般会给每个单选框提供value属性，指定其被选中后提交的值
                    *   checked属性，可以指定默认值
            *   file：文件选择框

            *   hidden：隐藏域，用于提交一些信息
            *   按钮：
                *   submit 提交按钮
                *   button 普通按钮
                *   image 图片按钮 
                    *   用src属性定义图片路径
    *   select：下拉列表
    *   子元素：option，指定列表的项
    *   texarea：文本域
        *   常用属性：
            *   cols
            *   rows
            *   均用于扩大文本框

### CSS：页面美化和布局控制

#### CSS: Cascading style sheets 层叠样式表

*   层叠：多个样式可以作用在同一个html的元素上，同时生效

*   好处：

    *   功能强大
    *   将内容的展示和样式的控制分离
        *   降低耦合度
        *   让分工更容易
        *   提高效率

*   CSS的使用：CSS与HTML结合方式

    *   内联样式

        *   在标签内使用style属性指定css代码，但是不推荐使用，依旧耦合
            *   举例：<div style="color: red">hello css</div>

    *   内部样式

        *   在head标签内，定义style标签，style标签的标签体内容就是css代码

            *   举例：

                <head>
                    <meta charset="UTF-8">
                    <title>内部样式</title>
                    <style>
                        div {
                            color: blue;
                        }
                    </style>
                </head>

    *   外部样式

        *   定义一个css资源文件，后缀为css

            *   例如：a.css文件

                ```
                div {
                    color: green;
                }
                ```

        *   在head标签内，定义link标签，引入外部资源文件

            *   例如

                ```
                <head>
                    <meta charset="UTF-8">
                    <title>外部样式</title>
                    <link rel = "stylesheet" href="../css/a.css">
                </head>
                ```

    *   注意：

        *   1，2，3种方式，css的作用范围越来越大

        *   方式1不常用，后期2，3常用

        *   第3种格式也可以写为：

            ```
            <head>
                <meta charset="UTF-8">
                <title>外部样式</title>
                <!--这样也可以-->
                <style>
                    @import "../css/a.css";
                </style>
            </head>
            ```

*   CSS基本语法：

    *   格式：

        *   选择器{属性名:属性值; 

            属性名:属性值; 

            属性名:属性值;...}

        *   选择器：筛选具有相同特征的元素

        *   注意事项：

            *   每一对属性的需要使用;隔开，最后一对属性可以不加;

*   选择器：筛选具有相似特征的元素

    *   分类

        *   基本选择器

            *   id选择器：选择器具体的id属性值的元素，建议在一个html页面中，id的值唯一
                *   语法：#id属性值{}
            *   元素选择器：选择有相同标签名的元素
                *   语法：标签名称{}
                *   注意：id选择器优先级高于元素选择器
            *   类选择器：选择具有相同的class属性值的元素
                *   语法：.class属性值{}
                *   注意：类选择器优先级高于元素选择器

        *   扩展选择器

            *   选择所有元素：
                
    *   语法：*{ }
                
    *   并集选择器：
            
        *   语法：选择器1，选择器2{ }
            
    *   子选择器：筛选选择器1元素下的选择器2
            
        *   语法：选择器1 选择器2 { }
            
        *   举例：
            
                    ```
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>Title</title>
                        <style>
                            div p {
                                color: green;
                            }
                        </style>
                    </head>
                    <body>
                        <div>
                            <p>23:06</p>
                        </div>
                        <p>2021/2/28</p>
                    </body>
                    </html>
            ```
            
    *   父选择器：筛选选择器2的父元素选择器1
            
        *   语法：选择器1 > 选择器2{ }
            
    *   属性选择器：选择元素名称，属性名=属性值的元素
            
        *   语法：元素名称[属性名=‘属性值’]{}
            
    *   伪类选择器：选择一些元素具有的状态
            
                *   语法：元素：状态{ }
                *   例如：<a>
                    *   状态：
                        *   link：初始化的状态
                        *   visited：被访问过的状态
                        *   active：正在访问的状态
                        *   hover：鼠标悬浮状态

*   属性：

    *   字体、文本
        *   font-size：字体大小
        *   color：文本颜色
        *   text-align：对齐方式
        *   line-height：行高
        
    *   背景
        
        *   background
        
    *   边框和轮廓
        
        *   border：设置边框，复合属性
        
    *   尺寸
        *   width
        *   height
        
    *   盒子模型：控制布局
        *   margin 外边距

        *   padding 内边距

            *   默认情况下内边距会影响盒子大小

                因此可以这样做：box-sizing: border-box;

                ```
                /*设置盒子的属性，让width和height是盒子最终大小*/
                box-sizing: border-box;
                ```

        *   浮动属性 float
            *   left
            *   right

        ![1614551920(1)](C:\Users\86180\Desktop\1614551920(1).png)

    

案例

![1614552951(1)](C:\Users\86180\Desktop\1614552951(1).png)

