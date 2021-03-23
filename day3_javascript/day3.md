# day3

## JavaScript

概念：一门客户端脚本语言

*   运行在客户端浏览器中，每个浏览器都有JavaScript的解析引擎
*   脚本语言：不需要编译，直接就可以被浏览器解析执行

功能：

*   可以增强用户和html页面的交互过程，可以来控制html元素，让页面有一些动态效果，增强用户体验



JavaScript = ECMAScript（客户端脚本语言的标准） + JavaScript自己特有的东西（BOM+DOM）



ECMAScript 客户端脚本语言的标准

*   基本语法
    *   与HTML的结合方式

        *   内部JS

            *   定义<script>，标签体内容就是js代码

        *   外部JS

            *   定义<script>，通过src属性引入外部js文件

        *   注意：

            *   <script>可以定义在html页面的任意位置，但是位置会影响执行顺序

            *   <script>可以定义多个

    *   注释

        *   单行注释： //注释内容
        *   多行注释： /**/

    *   数据类型

        *   原始数据类型（基本数据类型）：
            *   number：数字（整数、小数、NaN）
            *   string：字符串 "abc"， "a"， 'abc' 都是同一个东西字符串
            *   boolean：true和false
            *   null：一个对象为空的占位符
            *   undefined：未定义。如果一个变量没有给初始化，则会默认被赋值为undefined
        *   引用数据类型：对象

    *   变量

        *   变量：一小块存储数据的内存空间
        *   Java是强类型语言，JavaScript是弱类型语言
            *   强类型：开辟变量存储空间时，定义了空间将来存储的数据的数据类型。只能存储固定类型的数据
            *   弱类型：开辟变量才能出空间时，不定义将来的存储数据类型，可以存放任意类型数据
        *   语法：
            *   var 变量名 = 初始化值;

    *   运算符

        *   一元运算符：只有一个运算数的运算符 ++  --， +（正号）
            
            *   ++，-- 自增（自减），符号在前（先自增或自减后运算）
            
        *   算数运算符： + - * / % 
            *   +（-）：正负号
                *   在JS中，如果运算数不是运算符所要求的类型，那么js引擎会自动将运算数进行类型转换
                    *   其他类型转number：
                        *   string转number：按照字面值转换。如果字面值不是数字，则转为NaN
                        *   boolean转number：true为1，false为0
            
        *   赋值运算符：=， +=， -+

        *   比较运算符：>, <, >=, <=, ===(全等于)
            *   比较方式：
                *   类型相同：直接比较
                    *   字符串：按字典顺序比较，按位逐一比较，直到得出大小为止
                *   类型不同：先进行类型转换，再比较
                    *   全等于===：在比较之前，先判断类型，如果类型不同，直接返回false
            
        *   逻辑运算符：&& || !

            *   &&：与 （短路）
            *   ||：或（短路）
            *   !：非
                *   其他类型转boolean：
                    *   number：0或NaN为假，非0为真
                    *   string：除了空字符串（“”），其他都是true
                    *   null&undefined：都是false
                    *   对象：都是true

        *   三元运算符：？：

            *   ```
                var a = 3;
                var b = 4;
                
                var c = a > b ? 1 : 0; // a > b吗？如果a>b则走问号后面的1，反之走0
                alert(c)
                ```

    *   流程控制语句

        *   if else

        *   switch

            *   在java中，switch语句可以接受的数据类型：byte int char shor 枚举 String

                *   swtich(变量)：

                    ​	case 值：

            *   在JS中，switch可以接受任意类型的原始数据类型

        *   while

        *   do while

        *   for

    *   js特殊语法

*   基本对象

    *   Function

        *   创建：

            1.  var fun = new Function(形式参数列表，方法体); 不常用

            2.  function 方法名称（形式参数列表）{ 常用

                ​	方法体

                }

            3.  var 方法名 = function(形式参数列表) { 常用

                ​	方法体

                }

        *   属性：

            length：形参个数

        *   特点：

            方法定义时，形参类型不用写

            方法是一个对象，如果定义一个名称相同的方法，会覆盖

            在JS中，方法的调用只与方法的名称有关，和参数列表无关

            在方法声明中，有一个隐藏的内置对象（数组）,arguments，封装了所有的实际参数

        *   调用：

            方法名称（实际参数列表）；

    *   Array 数组对象

        *   创建：

            1.  var arr = new Array(元素列表)；
            2.  var arr = new Array(默认长度);
            3.  var arr = [元素列表];

        *   方法

            join(参数) 将数组中的元素按照指定分隔符拼接为字符串

            push() 向数组的末尾添加一个或更多元素，并返回新的长度

            ...

            更多参看官方文档

        *   属性

            length 数组的长度

        *   特点：

            *   JS中，数组元素的类型是可变的
            *   JS中，数组长度可变

    *   Boolean

    *   Date

        *   创建

            var date = new Date();

        *   方法

            toLocaleString()

            getTime()

            ...

            更多参看官方文档

    *   Math

        *   创建

            Math对象不需要创建，Math.方法名()直接使用即可

        *   方法

            random()

            round()

            ceil()

            floor()

        *   属性

            PI

    *   Number

    *   String

    *   RegExp 正则表达式

        *   正则表达式：定义字符串的组成规则

            具体看官方文档

        *   正则对象

            *   创建

                1.  var reg = new RegExp("正则表达式");
                2.  var reg = /正则表达式/;

            *   方法

                test(参数) 验证指定的字符串是否符合正则定义的规范

                具体看官方文档

    *   Global

        *   特点：全局对象，这个Global中封装的方法不需要对象即可直接调用

        *   方法：

            encodeURI()

            decodeURI()

            

            decodeURIComponent()

            encodeURIComponent()

            URL编码

            parseInt() 字符串转数字

            ​	逐一判断每个字符是否为数字，直到不是数字为止

            isNaN()

            ​	NaN什么都不认，连自己都不认，NaN参与的==比较全为false

            eval()

            ​	 计算 JavaScript 字符串，并把它作为脚本代码来执行

