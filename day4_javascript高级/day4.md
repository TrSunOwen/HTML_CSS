# day4

### DOM

概念：Document Object Model 文档对象模型

​	将标记语言文档的各个组成部分，封装为对象。可以使用这些对象，对标记语言文档进行CRUD的动态操作

W3C DOM 标准被分为3个不同的部分：

​	核心DOM - 针对任何结构化文档的标准模型

​		Document对象

​		Element对象

​		Attribute对象

​		Text对象

​		Comment对象

​		Node: 其他五个的父对象

​	XML DOM

​	HTML DOM

*   核心DOM 模型：
    *   Document文档对象
        *   创建（获取）：在HTML DOM 模型中，可以使用window.document
            1.  window.document
            2.  document
        *   方法：
            1.  获取Element对象
                1.  getElementById();
                2.  getElementsByTagName(); 返回数组
                3.  getElementsByClassName(); 返回数组
                4.  getElementsByName(); 返回数组
            2.  创建其他DOM对象：
            1.  createAttribute(name)
                2.  createComment()
                3.  createElement()
                4.  createTextNode()
        *   属性
    *   Element元素对象
        *   获取、创建：通过document对象获取和创建
        *   方法：
            *   removeAttribute()
            *   setAttribute()
    *   Node: 节点对象（其他五个的父对象）
        *   特点：所有DOM对象都可以被认为是一个节点
        *   方法
            *   CRUD DOM树：
                *   appendChild() 向节点的子节点列表的结尾添加新的子节点。
                *   removeChild()  删除（并返回）当前节点的指定子节点。
                *   replaceChild() 用新节点替换一个子节点。
        *   属性
            *   parentNode 返回节点的父节点
    
*   HTML DOM

    *   标签体的设置和获取：innerHTML

    *   使用HTML元素对象的属性

    *   控制样式

        *   使用元素的style属性来设置

            如：

            ```
                // 修改样式方式1
                div1.style.border = "1px solid red";
                div1.style.width = "200px";
            
                // font-size --> fontSize
                div1.style.fontSize = "20px";
            }
            ```

            提前定义好类选择器的样式，通过元素的className属性来设置class属性值

*   功能

    控制html文档的内容（增删改查）

    代码：获取页面标签（元素）对象 Element

    ​	document.getElementById(id值): 通过元素的id值获取元素对象

    操作Element对象：

     	1. 修改属性值
     	  	1. 明确获取的对象是哪一个
     	  	2. 查看API文档，找其中有哪些属性可以设置
     	2. 修改标签体内容
     	  	1. 属性：innerHTML

#### 事件监听机制（简称：事件）

概念：某些组件被执行了某些操作后，触发某些代码的执行。

​	事件：某些操作，例如：单击，双击，键盘按下了

​	事件源：组件。如：按钮，文本输入框...

​	监听器：代码

​	注册监听：将事件，事件源，监听器结合在一起。当事件源上发生了某个事件，则触发执行某个监听器代码

*   常见的事件：

    *   点击事件：

        *   onclick 当用户点击某个对象时调用的事件句柄。
        *   ondblclick	当用户双击某个对象时调用的事件句柄。

    *   焦点事件：

        *   onblur	元素失去焦点。

            一般用于表单验证

        *   onfocus	元素获得焦点。

    *   加载事件：

        *   onload	一张页面或一幅图像完成加载。

    *   鼠标事件：

        *   onmousedown	鼠标按钮被按下。

            ​	定义方法时，定义一个形参，接受event对象

            ​	event对象的button属性可以获取鼠标按钮键被点击了

            onmousemove	鼠标被移动。
            onmouseout	鼠标从某元素移开。
            onmouseover	鼠标移到某元素之上。
            onmouseup	鼠标按键被松开。

    *   键盘事件：

        *   onkeydown	某个键盘按键被按下。
            onkeypress	某个键盘按键被按下并松开。
            onkeyup	某个键盘按键被松开。

    *   选择和改变

        *   onchange	域的内容被改变。

            onselect	文本被选中。

    *   表单事件：

        *   onsubmit	确认按钮被点击。

            ​	可以阻止用户提交，方法返回false则阻止提交

            onreset	重置按钮被点击。

*   功能：某些组件被执行了某些操作后，去触发某些代码的执行
*   如何绑定事件
    *   直接在html标签上，指定时间的属性（操作），属性值就是js的代码
        *   事件：onclick--单击事件
    *   获取js获取元素对象，指定事件属性，设置一个函数

#### BOM

概念：Browser Object Model 浏览器对象模型

*   将浏览器的各个组成部分封装组成对象

    *   浏览器对象 Navigator
    *   显示器屏幕 Screen
    *   历史记录对象 History
    *   window窗口对象 Window
    *   地址栏 Location

*   Window窗口对象

    *   方法：

        *   与弹出框有关的方法 

            *   alert() 
            *   confirm()
                *   如果选择确定，则方法返回true；反之false 
            *   prompt()
                *   返回值：用户输入的值

        *   与打开关闭有关的方法

            *   close()

                注意：谁调用我，我关谁

            *   open()

                返回新Window对象

        *   与定时器有关的方法

            *   setTimeout() 按照指定的周期（以毫秒计）来调用函数或计算表达式

                参数：

                	1. js代码或者方法对象
                	2. 毫秒值

                返回值：唯一标识，用于取消定时器

            *   clearTimeout()	取消由 setTimeout() 方法设置的 timeout

            *   setInterval()	按照指定的周期（以毫秒计）来调用函数或计算表达式

                参数：

                 1. js代码或者方法对象
                 2. 毫秒值

                返回值：唯一标识，用于取消定时器

            *   clearInterval()	取消由 setInterval() 设置的 timeout

    *   特点

        *   不需要创建，直接调用即可。window.方法名();
        *   window引用可以省略。 方法名();

    *   属性：

        *   获取其他BOM对象：

            history

            location

            navigator

            screen

        *   获取DOM对象

            document

*   Location: 地址栏对象

    *   创建（获取）：
        1.  window.location
        2.  location

    *   方法：
        *   reload() 重新加载当前文档，刷新
    *   属性：
        *   href 设置或返回完整的URL

*   Histroy：历史记录对象

    *   创建（获取）：

        1.  window.history

        2.  history

    *   方法：

        *   back()

        *   forward()

        *   go()

            参数：

            ​	正数：前进几个历史记录

            ​	负数：后退几个历史记录

    *   属性：

        *   length 返回当前窗口历史记录列表中URL的数量