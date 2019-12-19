<font style="font-size:1.3em;font-weight:bold;"> 目录 </font> 
[toc]

# Js简介
    JavaScript 简称"Js"
        应用: 
            * 数据验证 (初衷)
            * 网页特效
            * 游戏
            * App
            * 私下里跟后端做些事情 
            * ...
        
        历史:
            1992年, 一个叫 Nombas 的公司, 研发了一门语言叫 "C减减"(C-minus-minus, 简称"Cmm"), 是一款能够在浏览器端运行的脚本语言, 主要用于表单数据的验证, 例如 "密码是否相同", "是否有表单未填写"等.  后来由于 C减减的名字太特殊, 改名为 "ScriptEase".


           后来, 最早的浏览器公司"网景" (Netscape) 发现网络越来越发达, 网页内容也越来越多, 表单验证的时间越来越长, 用户体验感极速下降. 于是也想开发一个类似于 ScriptEase 的语言, 来解决这样的问题.  

           1995年, 网景公司成功研发LiveWire脚本语言, 以代替ScriptEase, 应用于 Netscape Navigator 2.0, 后更名为 "LiveScript"

           同年(95年), Netscape Navigator 2.0 Beta 3 发行时, 又将 "LiveScript" 更名为 "JavaScript", 目的是想蹭蹭 Java的热度, 当时导致了很多程序员对这门语言有诸多误解.



           三分天下: 
               因为 Js 比较成功, 所以 "微软" 也来参了一脚, 发行"JScript" 

               Nombas 的 ScriptEase
               Netscape 的 JavaScript
               Microsoft 的 JScript

           标准化:
               由于三门语言效果一样 且 互不兼容, 所以在1997年, 为了有更统一的标准, ECMA协会综合多个大牛, 重新定义了名为  "ECMAScript" 的全新脚本语言, 简称 "ES"
               至今, ES已经发展到了 ES6

           由于ES 是Js提交的草案, 所以Es 有很多标准是采用的Js, 导致很多人把Js和Es就理解为一个人了. 所以我们现在所说的Js, 基本就是再说Es, 简单理解: Js是通俗说法,  Es是标准说法.

        Js学习内容
            1. 核心知识        ECMAScript
            2. 文档对象模型    DOM
            3. 浏览器对象模型  BOM
            4. 框架
                基础框架: JQuery, BootStrap
                高级框架: Vue, React, Angular


        注意点: 
            * Js 是一门客户端的脚本语言, 也有服务端的Js版, 例如: Node.js
            * Js 是不能读写客户端上的文件 (除了浏览器的Cookie文件)
            * Js 是不能写服务端上文件, 只可以读取

# 浏览器引擎
    每一个浏览器都有一个强大的内核, 来支撑着画面的渲染 和 数据的计算
        浏览器内核分成两部分: 渲染引擎 + Js引擎

        渲染引擎:
            根据HTML代码, 向网页显示各种文字, 图形, 视频等元素 以及 对内容, 图形做各种排版
            
            各大浏览器的渲染引擎: 
            * IE - Trident 引擎
            * FIrefox - Gecko引擎
            * Chrome/Safari - Webkit引擎
            * Opera - Presto引擎
            * Chrome+Opera 联合开发的 Blink 引擎

        Js引擎:
            读取网页中的js代码, 并对其进行处理. 例如: 加减运算, 事件调用

            各大浏览器的Js引擎:
            * 旧IE - JScript 引擎
            * IE9 - Chakra 引擎
            * IE Edge - Chakra 引擎
            * Firefox - monkey 引擎
            * Safari - SquirrelFish Extreme 引擎
            * Opera - Carakan 引擎
            * Chrome - V8引擎 ( Node.js 也封装的V8引擎)

# js使用
    <!-- 1. 外部导入 -->
    <script src="./demo.js"></script>
    
    <!-- 2. 内部现写js -->
    <script>
        alert('内部书写js代码');
    </script>
    
    <!-- 3. 事件触发js -->
    <!--    事件有很多,  onclick 是单击事件 -->
    <button onclick='alert("真爽")'>点我一下</button>

# Js语法
    1. 分号
        Js的每一条语句通常以 分号 结尾, 代表该语句已经结束.
        用分号结束的语句, 可以并列在一行上.

        推荐: 每条语句加分号
        
    2. 空格
        在运算符的前后, 添加空格, 以增加代码的可读性
        
    3. 单行代码长度
        为了提交代码的可读性, 一行代码最好不超过80个字符
        
    4. 代码块 { }
        代码块由一对花括号组成 {  }
        作用: 一次性执行多条语句(捆绑执行)

        后期函数经常用
    
    5. 大小写
        Js 严格区分大小写
        
    6. 保留字, 关键字
        在js中, 保留字, 关键字是不能作为变量, 函数使用的

        常见关键字, 保留字: 
           break    case    catch   continue    default
           delete   do      else    finally     for
           function if      in      instanceof  new
           return   switch  this    throw       try
           typeof   var     void    while       with

        更全面的保留字, 关键字有哪些?
            参考地址: https://www.runoob.com/js/js-reserved.html
    
     7. 注释
        单行注释: // 注释内容   
        多行注释: /* 注释内容 */
        
        注意: 多行注释不要嵌套使用

# 变量
    1. 变量
        存储数据的容器, 类似于数学中的未知数

    2. 定义变量
        var 变量名;
        var 变量名 = 值;
        var 变量名 = 值, 变量名 = 值, 变量名 = 值, ....
        
        将 内容 输出到浏览器中
         * 控制台输出:  console.log( 内容 )
         * 页面输出:  document.write( 内容 )
    
    3. 标识符, 标记
        每一个变量都有一个标记, 就是变量名

        标识符命名规范
        * 可包含数字, 字母, 下划线 和 $美元符号
        * 不能以数字开头
        * 不能使用关键字, 保留字
        * 区分大小写
        * 取名要有意义, 以提高代码的可读性

    4. 未定义变量
        没有定义过的变量, 则被称之为"未定义变量"
        未定义变量 是不能直接使用的, 一旦使用, 则会报错
        解决方案: 先定义变量, 再使用
        
    5. 常用命名规则

        驼峰式命名法:从第二个单词开始,首字母大写(小驼峰)
        帕斯卡命名法:每个单词的首字母都大写(大驼峰)
        匈利亚命名法:每个单词之间用 下划线 隔开
    
    6. 变量提升 Hoisting

        提升（Hoisting）是 JavaScript 将声明移至顶部的默认行为。
        可以在声明变量之前使用它
        注意: 初始化不会被提升
        
    7. 关键字: let 和 const

        let 关键词是声明块作用域的变量
        在代码块块 {} 内声明的变量,外部无法访问
        
        const: 经常不变的量,被称之为"常量"
        const 定义的变量与 let 变量类似，但不能重新赋值
        const 变量必须在声明时赋值

# 数据类型string
    数据类型
        数据一共有如下几种形态: 
        * string
        * number
        * boolean
        * null
        * undefined
        * object
        * array
        * function
        * symbol    ES6 新加的
    
    1. String 字符串
        可包含数字, 字母, 下划线, 汉字, 标点等众多字符
        主要表现形式: 单引号 or 双引号

        注意: 单双引号没有区别
        
    2. 字符串长度
        一个字符串最好不超过80个字符
    
        如果超过, 建议在字符串的适当位置, 进行折行 ( 通过 \ 可折行 )
        
    3. 变量识别
        如果字符串中出现了变量, 单双引号无法识别, 但是反引号是能识别变量
        反引号: `` 
        反引号中的变量格式: ${变量名}
        
    4. 转义字符
        转义符: \
        通过转义符将 普通字符 => 特殊字符
        通过转义符将 特殊字符 => 普通字符

        特殊字符: 本身就具备特殊意义的的字符, 例如: 单引号, 双引号, 转义符本身

        特殊字符 => 普通字符
            \'
            \"
            \\

        普通字符 => 特殊字符
            \n      换行
            \r      回车
            \t      制表符, tab键

        注意: 单双引号可以互插, 不能自插
        
    5. 拼接符 + 
        字符串 与 其余字符串or数字相加, 此处并非加法, 而是拼接

        小结: 与字符串相加, 都是拼接
        
    6. 获取字符串长度
        字符串名.length
        
    7. 类型获取
        typeof
        
    8. 其余类型 如何转为 字符串类型
        String()
        .toString()

# 数据类型number
    1. number有几种形态
        整数
        小数, 浮点数
        NaN: Not a Number
            NaN与任何数进行运算, 结果都是: NaN
            NaN与任何数进行比较, 结果都是: False
            0/0 的结果: NaN

        科学计数法 (超大的数字)
            mEn : m * 10的n次方

            2E3 = 2 * 10的3次方

            字母E 可大写,可小写

        无穷大
            Infinity     正无穷
            -Infinity    负无穷

            因为内存限制, 最大值: 1.7976931348623157e+308
                          最小值: 5e-324

                         超过 1.7976931348623157e+308 为 Infinity
                         超过 -1.7976931348623157e+308 为 -Infinity
                         超过 5e-324 为 0
                         超过 -5e-324 为 -0
    
    2. 其余类型 => number类型

        Number()        转为number数字
        parseInt()      转为整数int
        parseFloat()    转为小数, 浮点数float

# 数据类型Boolean
    1. Boolean 布尔
            值: true 或 false     (只能用小写)

            分别代表两种极端的状态: 对/错  是/否  开/关
        
    2. 场景: 常被用于比较, 条件判断

    3. 如何转为boolean型
        Boolean()

        有如下几种数据会转为false, 其余都是true
        * 0
        * 0.0
        * -0
        * NaN
        * '' 
        * null
        * undefined
        * false     
        
# 数据类型function
    1. function 函数
        很多编程语言都有函数, 将多条语句进行封装(捆绑), 形成一个完整的功能

        目的: 
            定义一次代码, 可多次使用
            传递不同的参数, 可产生不同的结果 
    
    2. 定义函数
        function 函数名( 参数 ){
            代码块
        }

    3. 调用函数
        函数名()

    4. 返回值
        格式: return 内容
        
        通过return 返回数据 到调用函数的地方, 并且立马结束函数

# 数据类型array
    1. Array 数组
            可理解为是: 容器
            可存储多个任意类型的数据, 并且为数据分配编号, 
            第一个数据编号为0, 第二个数据编号为1, 以此类推
    
    2. 定义数组
        格式:  [数据, 数据, 数据, 数据]

    3. 读取数据
        根据编号来读取数据
        格式:  数组变量[编号]

    4. 修改数据
        根据 已有的编号, 重新赋值

    5. 添加数据
        根据 没有的编号, 重新赋值
        一般情况下, 编号都是连续设置的, 中间中断了, 那么以 undefined 代替

    6. 删除数据
        方法1: 清空数组  
                数组变量 = [];
        方法2: 删除数据, 保留编号
                delete 数组变量[编号]
        方法3: 连编号一起删, 后面的编号会依次向前推
                数组变量.splice(编号, 个数)

    7. 类型获取
        array 的类型是: object
        在未来, 一切皆对象
    
# 数据类型 object
    1. Object 对象
            与Array类型, 都是容器
            Array 给数据分配 编号
            Object  给数据分配 属性, 有更高的代码可读性

    2. 定义
        {
            属性: 值,
            属性: 值,
            属性: 值,
            ...
            方法: function(){
                代码块
            },

            方法: function(){
                代码块
            },
            ...
        }

        一个对象由: 属性 和 方法 组成
        属性: 类似于编号, 不过可读性更高
        方法: 函数的另一种表达方式

    3. 使用属性
        对象变量.属性

    4. 使用方法
        对象变量.方法()
        
# null+undefined
    1. undefined
        可理解为: 不存在

        有如下几种情况的值为 undefined
        * 变量已声明, 却未赋值, 则默认为undefined
        * 对象属性未赋值, 则默认为undefined
        * 调用函数时, 应该提供的参数却没给, 则默认为undefined
        * 函数没有返回值, 默认返回undefined
    
    2. null 
        可理解为 空

        一般情况下, null都是手动赋予的, 常用于占位

        与undefined 的区别
        * null 是关键字, undefined不是关键字
        * null 的类型是: object         Js的历史遗留Bug
        * undefined的类型是: undefined
        
    null 和 undefined 值相等,但类型不同

# Symbol    
    Symbol 是 ES6 引入了一种新的原始数据类型，表示独一无二的值
    小数转为 二进制时, 结果有误差

# 数据分类
    1. 所有数据分为两类: 
            原始类型: string, number, boolean, null, undefined, symbol
            引用类型: array, object, function
        
    2. 原始类型
        原始值, 存储"栈内存"中, 内存直接存储的是: 值
        var x = 10;
        var y = x;  // 变量y 拷贝了 变量x 的值, 变量x 和 变量y 是两个不同的内存
        y = 20;
        console.log(x, y); // 修改y 的值不会影响 变量x 的值
        console.log;
    
    3. 引用类型
        引用值, 存储"堆内存"中, 内存直接存储的是: 地址, 由地址指向值
        var x = [10,20,30];
        var y = x;  // 将变量x的地址给了 变量y
        y[0] = 99;  // 变量y 一旦发生变化, 其余指向该地址的变量, 都会被迫受到影响
        console.log(y);
        console.log(x);
        
     栈内存: 可直接访问 存储空间大小固定 空间小, 效率高​
     堆内存: 通过地址来引用具体的值 存储空间大小不固定 空间大, 效率低

# 类型转换
![join](https://note.youdao.com/yws/public/resource/bcd74097c9c19078fc7b2e45d1a2af9c/xmlnote/WEBRESOURCE1c5ae5beb9718d04ba818ff6b5ce7265/4246)
   
    1. 转为number
            Number()
                字符串: 只有正常的数字, 小数, 科学计数法保留数字
                布尔: 
                    true => 1
                    false => 0
                null => 0
                undefined => NaN

            parseInt()
                字符串: 
                    数字开头的, 保留到第一个字母之前的所有数字
                    字母开头, NaN
                boolean, null, undefined => NaN

            parseFloat()
                字符串:
                    数字开头的, 保留到第一个字母之前的所有数字(除了第一个字母e 和 小数点)
                    字母开头, NaN
                boolean, null, undefined => NaN
        
        // number 与 其余类型 运算时(string的+除外),  其余类型 自动转为 number
        console.log(5 - '2');  // 3
        console.log(5 - '2a'); // NaN
        console.log(5 - 'a2'); // NaN
        console.log(5 - true); // 4
        console.log(5 - null); // 5
        console.log(5 - undefined); // NaN
        console.log(5 + true); // 6
        console.log('------------- 分隔符 --------------');

        console.log(true - '2'); // -1  相当于 1-2 = -1
        console.log(null - '2'); // -2  相当于 1-2 = -1
        console.log(undefined - '2'); // NaN  

    2. 转为string
        String() : 任何数据都可以原封不动转为字符串
        .toString()

    3. 转为boolean
        Boolean()
        
        var x = Boolean(0);
        var x = Boolean(0.0);
        var x = Boolean(-0);
        var x = Boolean(NaN);
        var x = Boolean(null);
        var x = Boolean(undefined);
        var x = Boolean(false);
        var x = Boolean('');
        // 以上都能转为false, 其余值都只会转为true

# 运算符
    算术运算符
        + - 
        *  乘法
        /  除法
        %  取模,  求余数

    自增自减运算符
        ++  
        -- 
    
        a++: 先返回a, 再a = a + 1
        ++a: 先a = a + 1, 再返回a

    赋值运算符
        =
        +=      a += b  ===>  a = a + b 
        -=      a -= b  ===>  a = a - b
        *=
        /=
        %=      a %= b  ===>  a = a % b

        = 优先算右侧, 再算左侧
        = 左侧不能做运算


    比较运算符
        比较结果: boolean值
        >  >=
        <  <=
        ==      比较两边的值是否相等
        ===     全等: 比较两边的值是否相等 且 两边的数据类型是否相等
        !=      
        !==     不全等: 只要全等时为false, 其余都是true
    
    逻辑运算符
            逻辑与 &&
            逻辑或 ||
            逻辑非 !
    
    位运算符
                  运算符       运算规则
        按位与     &           一个为0即为0, 否则为1
        按位或     |           一个为1即为1, 否则为0
        按位异或   ^           相同为0, 相异为1
        按位取反   ~           ~x = -x-1
        左移       <<          左移n位, 低位补0
        右移       >>          右移n位, 正数: 高位补0
                                        负数: 高位补1
        右移       >>>         右移n位, 高位补0, 带符号

        注: 
          * 了解原码, 反码, 补码
          * >> 和 << 和 <<< 正数位移: 
                             * 求原码
                             * 左右位移
          * >> 和 << 负数位移: 
                             * 把负数当正数用
                             * 求补码
                             * 左右位移
                             * 减1
                             * 求反码
                             * 加符号位
          * >>> 负数位移:
                        * 把负数当正数用
                        * 求补码
                        * 左右位移
        
        运算技巧
          * << 相当于 乘以2的n次方
          * >> 相当于 除以2的n次方
          * 按位或0, 按位异或0, 两次取反0, 左移0位 都能取整
          * 交换两个变量的值
    
        var x = 10;
        var y = 7;
        var z = -10;

        // 1010
        // 0111
        // -----
        // 0010  = 2
        console.log( x & y );  // 2                 

        // 1010
        // 0111
        // -----
        // 1111 = 15
        console.log( x | y );  // 15 


        // 1010
        // 0111
        // -----
        // 1101 = 13
        console.log( x ^ y );  // 13     

        // ~x : -x-1 = -10-1 = -11
        console.log( ~x );     // -11



        //      32位
        // 10 的原码: 00000000000000000000000000001010
        // 10 的反码: 11111111111111111111111111110101
        // 10 的补码: 11111111111111111111111111110110


        // 10 的原码: 00000000000000000000000000001010
        // 左移1位:  000000000000000000000000000010100
        //            00000000000000000000000000010100 = 20
        console.log( 10 << 1);  // 20

        // 10 的原码: 00000000000000000000000000001010
        // 右移1位:   000000000000000000000000000001010
        //            00000000000000000000000000000101 = 5
        console.log( 10 >> 1);  // 5

        // 10 的原码: 00000000000000000000000000001010
        // 10 的反码: 11111111111111111111111111110101
        // 10 的补码: 11111111111111111111111111110110   也是-10的原码
        // 左移1位:  111111111111111111111111111101100
        //            11111111111111111111111111101100
        // 减1:       11111111111111111111111111101011
        // 反码:      00000000000000000000000000010100 = 20
        // 加符号:   -20
        // 
        console.log( -10 << 1 );


        // 10 的原码: 00000000000000000000000000001010
        // 10 的反码: 11111111111111111111111111110101
        // 10 的补码: 11111111111111111111111111110110   
        // 右移1位:   011111111111111111111111111110110
        //            01111111111111111111111111111011 = 2^31 -1 - 4 
        //                                                = 2147483643‬
        console.log( -10 >>> 1 );


        // <<   左移n位, 低位补0
        // >>   右移n位, 正数: 高位补0
        //               负数: 高位补1
        // >>>  右移n位, 高位补0, 带符号

        // * >> 和 << 和 >>> 正数位移: 
        //                             * 求原码
        //                             * 左右位移
        // 
        // * >> 和 << 的负数位移: 
        //                      * 把负数当正数
        //                      * 求补码
        //                      * 左右位移
        //                      * 减1
        //                      * 求反码
        //                      * 加符号
        // 
        // * >>> 负数位移: 
        //               * 把负数当正数
        //               * 求补码
        //               * 左右位移

        // 1111 = 2^4 -1 = 16 - 1 = 15
        // 1110 = 2^4 -1 -1 = 14
        // 1101 = 2^4 -1 -2 = 13
        // 0111 = 2^4 -1 -8 = 7
        console.log('------------- 分隔符 --------------');


        console.log( 6 >> 1 ); // 6 / 2^1 = 6/2 =3
        console.log( 6 << 1 ); // 6 * 2^1 = 6*2 =12
        console.log( 6 << 2 ); // 6 * 2^2 = 6*4 =24


        // 小数转换成整形
        console.log( 6.3 | 0 );
        console.log( 6.3 ^ 0 );
        console.log( 6.3 << 0 );
        console.log( ~~6.3 );


        // 交换两个变量的值

        // 1. 经典写法 (利用第三方变量, 临时变量)
        var x = 10;
        var y = 5;
        var tmp = x;
        x = y;
        y = tmp;
        console.log(x,y);


        // 2. 高效写法 (没有第三方变量, 内存就节省了一些)
        var x = 10;
        var y = 5;

        x ^= y
        y ^= x 
        x ^= y
        console.log(x, y);

# 简易DOM操作
    1. 获取标签对象
        * 通过id获取        格式: document.getElementById('id名')
        * 通过class获取     格式: document.getElementsByClassName('class名')
        * 通过标签获取      格式: getElementsByTagName('标签')
        * 通过name获取      格式: getElementsByName('name名')
        
    2, 设置/获取css
        格式: 对象.style.css属性名 
        
    3. 查看对象
        console.log(对象)
        console.dir(对象)     能看到大多数的通用属性
        
# 流程控制-分支
    1. if分支
        if单向分支
            if( 条件表达式 )  一条语句

            if( 条件表达式 ){
                代码块
            }

        if双向分支

            if( 条件表达式 ){
                代码块
            }else{  
                代码块
            }

        if多向分支

            if( 条件表达式 ){
                代码块
            }else if( 条件表达式 ){  
                代码块
            }else if( 条件表达式 ){  
                代码块
            }else if( 条件表达式 ){  
                代码块
            }else if( 条件表达式 ){  
                代码块
            }else{
                代码块
            }

            注意: 
                * else 和 if 之间必须要有空格
                * 最后一个else 可写可不写

        if巢状分支
            if( 条件表达式 ){
                if( 条件表达式 ){
                    if( 条件表达式 ){
                        if( 条件表达式 ){
                            代码块             必须同时满足前面的所有条件
                        }else{
                            代码块
                        }   
                    }else{
                        代码块
                    }
                }else{
                    代码块
                }
            }else{
                代码块
            }
            
    2. switch分支
        switch(标记){
            case 标记1: 代码块; break;
            case 标记2: 代码块; break;
            ...
            case 标记N: 代码块; break;
            default: 代码块;
        }

        注: 
         * break 能立马结束switch分支
         * 每个case 的代码块没有break, 会依次向下执行
         * 匹配不到标记是, 默认执行default, 如果没有default, 则结束switch
         * 标记只能匹配同类型数据, 不能匹配等价数据
         
# 流程控制-循环
    功能相似, 代码位置相同, 用循环
    功能相似, 代码位置不同, 用函数


    常用循环
    1. while
    2. do/while
    3. for
    4. for/in

    循环三要素
    * 初始值
    * 循环条件  (表达式的最终结果是否为 true)
    * 循环增量  (不代表只能+, 也可以减, 乘, 除, 与或非...)


    1. While循环
        
        初始化
        while( 条件表达式 ){
            代码块
        }
    
    2. doWhile循环
        
        do{
            代码块
        }while( 条件表达式 )
        
      while 和 doWhile 之间的区别
         * while 是先判断再执行
         * doWhile 是执行1次, 再判断再执行
         
    3. for 循环
        for(初始值 ; 循环条件; 循环增量){
            代码块
        }
    
    4. for/in 循环
        遍历对象而准备的循环

        for(变量 in 对象){
            代码块
        }

        变量 获取的是: 属性名
        对象[变量] 获取的是: 属性值
    
    5. 无限循环
        俗称"死循环", 只要 循环条件永远成立 即可形成死循环
        当不知道要循环多少次时, 即可使用 无限循环

        将来的应用场景: 轮播无限滚动, 字幕滚动
        
    6. 流程控制符(保留字)
        * continue      立马结束当前一轮循环, 准备下一轮循环
        * break         立马结束循环orSwitch分支, 准备执行循环/分支外的代码
        
         注:
           for(){
               for(){
                 break;   // 只能跳出包含自己的最近循环
               }
           }
         

            for(){

                for(){
                       // 只能跳出包含自己的最近循环
                }

                if(){

                }else{
                    break;

                }

            }
# 函数
    split() 方法用于把一个字符串分割成字符串数组。
    reverse() 方法用于颠倒数组中元素的顺序。
    join() 方法用于把数组中的所有元素放入一个字符串。
    
# 内置对象
     一切皆对象   
    内置对象
        Number
        String
        Boolean
        Array
        Date
        Math
    
    // Number对象
        var x = 10;  // number 类型, 推荐写法
        var y = new Number(10);  // object 类型, 少用
    
# 函数定义
    函数4种方式: 
        1. 函数声明
            function 函数名( 参数1, 参数2, ... ){
                代码块
            }

        2. 函数表达式
            变量 = function ( 参数1, 参数2, ... ){ 
                代码块
            }

        3. 构造器
            变量 = new Funtion('参数1', '参数2', '参数3', ..., '代码块')

        4. 箭头函数
            (参数1, 参数2, ... ) => { 代码块 }
            (参数1, 参数2, ... ) => 表达式 等同于 (参数1, 参数2, ... ) => { return 表达式 }


        注: 
         * 函数声明后, 是需要调用才会执行
         * 函数表达式不需要再取一个有意义的函数名而烦恼
         * 构造器的参数必须是 string类型 (效率较低, 使用较少)
         * 箭头函数 是ES6新增,  有简化, 隐式返回等多种好处
         
# 函数使用
    1. 使用函数
        函数在声明之后, 默认不会自动执行, 需要调用才能执行
        使用函数有两种情况: 
        * 调用函数:  函数名() 
        * 引用函数:  函数名
            function demo(){
            return "1111111";
            }

            var x = demo(); // 调用函数
            var x = demo;   // 引用函数,  变量x 存储的是 函数的内存地址
            console.log(x);
    
            console.log( x() ); // 通过 函数地址 调用函数
    
     2. window对象
        window 是js最高的对象, 代表浏览器
        作用: 全局能用的都属于 window对象的属性or方法
            var x = 10;
            console.log(x);
            console.log(window.x);  // 变量x 当成window对象的属性
    
            function demo(){
                console.log('我是一个 demo函数');
                var y = 20; // 变量y 属于demo, 不归window管
                console.log(window.y); // undefined
            }
    
            demo();
            window.demo();
    
            console.log(window);
    
    3. this对象
            this 是关键字, 代表当前对象, 并非变量
            函数内的this => window对象
            注: 
             * 普通函数内的this, 代表window对象
             * 被某元素的事件触发的函数, this代表当前元素对象
             
# 函数-返回值
    1. 关键字 return
        作用1: 将数据返回到 调用函数的地方
        作用2: 立马结束函数
        
    2. 返回类型
        可返回任意类型

        小技巧: 可通过数组, 一次性返回多个值
    
     3. 无返回值
        函数没有return时, 默认返回undefined
        
# 函数-参数
    1. 参数分类
        形式参数: 俗称"形参", 定义函数时给的参数
        实际参数: 俗称"实参", 调用函数时给的参数
        
    2. 默认参数
        形参没有默认值, 形参默认采用 undefined
        形参有默认值, 形参采用指定默认值
        
    3. 参数规则
        * 不限制参数数据类型
        * 不检查参数数据类型
        * 不限制参数个数


        实参个数 = 形参个数 : 完美
        实参个数 > 形参个数 : 先来后到, 抛弃后来的实参
        实参个数 < 形参个数 : 先来后到, 多余的形参, 采用undefined
        实参个数不确定时 : 使用 arguments 对象读取所有的实参
        
        function sum(){

            // 累加方法1
            // var sum = 0;
            // sum += arguments[0];
            // sum += arguments[1];
            // sum += arguments[2];
            // sum += arguments[3];
            // sum += arguments[4];


            // 累加方法2
            var sum = 0;
            for(var i = 0; i < arguments.length; i++){
                sum += arguments[i];
            }

            console.log(sum);

        }
        sum(10,20,30,40,50);
        sum(10,20);

# 作用域
    1. ES5 作用域
        * 全局变量: 在函数外定义的变量
        * 局部变量: 在函数内定义的变量
    
    2. 作用域链
        局部环境: 能解析全局变量
        全局环境: 不能解析局部变量
                  (可以解析没有用 var 声明的变量)
        
        作用域链: 
            当前作用域 > 其余作用域   
        
        function demo3(){
            var y = 20; // 局部变量
            z = 30; // 可当做是: 全局变量
        }   

        demo3();
        // console.log(y); 
        console.log(z);
        
        当前作用域 > 其余作用域
        如果当前作用域找不到, 再去上面的作用域找
        
    3. ES6 作用域
        var 声明的变量: 全局作用域
        let 声明的变量: 块级作用域

        块级作用域可大可小
        
        {
            // 当前块级作用域
                var x = 1;
                let y = 2;  // let 在哪个作用域声明, 作用域就只能在哪里
                console.log(x,y);
        }

        // 块级作用域外
        console.log(x);
        // console.log(y);

        var m = 5;
        let n = 6; // 此时的let n 是在全局作用域声明
        
        扩展知识: 
         * 有var 和 没有var 的区别
         
# 自执行函数
    1. 自执行函数
        格式: ()()

        注: 
         * 第一个() 里面是写: 匿名函数
         * 第二个() 代表: 启动(调用)当前函数
         
        特性: 
         * 定义完函数时, 就立马自我调用
         * 无需取名
         * 重点: 自成一域(独自创建一个作用域, 作用域里面的变量外面是访问不到, 该行为: 避免变量污染)
         
         <ul>
        <li>李白</li>
        <li>阿珂</li>
        <li>韩信</li>
        <li>赵云</li>
        </ul>
    
        var li = document.getElementsByTagName('li');

        for(var i = 0; i < li.length; i++){

            li[i].onclick = function (){
                console.log(i);
                // console.log(this);
            }
        }
        
        // Bug: 总是获取的最后一个编号
        // 原因: 这里的变量i 的作用域是贯穿全局的
        // 解决方案: 将 函数独自成为一个作用域, 不再受外界影响


        // 自执行写法
        for(var i = 0; i < li.length; i++){
            (function(m){
                li[m].onclick = function (){
                    console.log(m);
                }
            })(i);
        }
        
# 闭包
    闭包: 
     在函数A 里面定义函数B, 并返回函数B, 即可形成闭包
    
    优势: 
     * 可使得函数B的生命周期得到延长, 长期保存在内存中
    
    劣势:
     * 由于函数B 的生命周期延长, 内存不能及时释放, 内存消耗变大, 效率变低

# Call和Apply
    1. call() 方法
        作用: 对象A 通过call 借用对象B, 那么对象A内的this就指向对象B
    
    2. apply() 方法
        作用: 对象A 通过call 借用对象B, 那么对象A内的this就指向对象B
    
    3. call方法 和 apply方法的区别
        * call 和 apply 功能是一模一样
        * call 是分别接收参数
        * apply 是接收数组参数

# 对象-创建
    1. 创建对象
        * Json创建    (推荐)
        *   {
        *       属性名: 属性值,
        *       属性名: 属性值,
        *       ...
        *
        *       方法名: function(){},
        *       方法名: function(){},
        *       ...
        *   
        *   }
        *
        *
        * 对象构造器
        *   对象变量 = new Object()
        *   对象变量.属性名 = 属性值;
        *   对象变量.属性名 = 属性值;
        *   ...
        *
        *   对象变量.方法名 = function(){}
        *   对象变量.方法名 = function(){}
        *   ...
        *
        * 自定义构造器
        *   function 构造器名(){
        *       this.属性名 = 属性值;
        *       this.属性名 = 属性值;
        *       ...
        *
        *       this.方法名 = function(){}
        *       this.方法名 = function(){}
        *       ...
        *   }
        *
        *
        *   对象变量 = new 构造器名()
        *
        * 匿名构造器
        *   new function(){
        *       this.属性名 = 属性值;
        *       this.属性名 = 属性值;
        *       ...
        *
        *       this.方法名 = function(){}
        *       this.方法名 = function(){}
        *       ...
        *   }
    
    注: 
     * Json格式中, 属性名也被称之为: 键,  键与值配合一起称之为: 键值对
     * Json格式中, 每一键值对之间用 "逗号" 隔开

# 对象-使用
    1. 使用属性
            * 对象.属性名
            * 对象[属性名]

    2. 使用方法
        * 对象.方法名()


    注: 
     * 比较奇葩的属性名 or 纯数字属性名 or 数字开头的属性名, 建议用 [] 来访问

# 对象-原型
    原型 prototype
        能在原型对象上添加属性/方法

# 数组
    1. 创建数组
        * Json 方式 (推荐)
        * 构造器
        
    注: 
     * 数组的每一个zhi,都会分配一个索引(编号)
     * 索引都是连续的, 如果跳跃式添加, 中间以undefined代替
     
     // 构造器
        var list = new Array();
        var list = new Array(1,2,3);
        console.log(list);
    
    2. 多维数组
        将数组的值 指定为数组(数组嵌套数组), 即为多维数组
        
    3. 遍历数组
        <ul>
            <li>李白</li>
            <li>阿珂</li>
            <li>兰陵</li>
            <li>悟空</li>
        </ul>
      
        for
        var list = ['迪丽热巴','古力娜扎','马尔扎哈','真皮沙发'];
        for(var i = 0; i < list.length; i++){
            document.write( list[i] );
        }
        
        for/in
        for(var i in list){
            document.write(i);      // 读取索引
            document.write(list[i]); // 读取值
        }

        var li = document.getElementsByTagName('li');
        for(var i = 0; i < li.length; i++){
            li[i].style.color = 'red';
        }
        
# 计时器
    1. 单次计时
        多少时间之后, 就做一次指定事情, 常被用于: 延迟
        setTimeout(事情, 时间)

    2. 多次计时
        每隔多少时间之后, 就做一次指定事情, 常被用于: 定时
        setInterval(事情, 时间)

        时间单位: 毫秒

    3. 计时器id
        每个计时器都会返回id, 用以证明该计时器的编号, 方便后期的清除计时器

    4. 清除计时器
        clearTimeout(计时器id)
        clearInterval(计时器id)

# 事件
    1. 事件绑定
        * 事件属性
        *      <开始标签  事件属性名="js代码">
        * 
        * 对象属性
        *      对象.事件属性 = function(){ js代码块 }
        * 
        * 事件监听
        *      非IE: 对象.addEventListener('事件', 函数名, false)
        *      老IE: 对象.attachEvent('on事件', 函数名, false)
    
    2. 事件解绑
        * 对象.事件 = null
        * 对象.事件 = function(){}   空函数
        * 取消监听
        *   非IE: 对象.removeEventListener('事件', 函数名)
        *   老IE: 对象.detachEvent('on事件', 函数名)

# 常用鼠标事件
    鼠标事件
        onclick         单击
        ondblclick      双击
        oncontextmenu   右击
        onmouseover     划入
        onmouseout      划出
        onmousedown     按下
        onmouseup       松开
        onmousemove     移动
        
        <button onclick="alert('迪丽热巴')">单击</button>
        <button ondblclick="alert('古力娜扎')">双击</button>
        <button oncontextmenu="alert('马尔扎哈')">右击</button>
    
    
        <div id="box"></div>
        <script>
            var box = document.getElementById('box');
    
            box.onmouseover = function(){
                box.innerHTML = '划入';
            }
    
            box.onmouseout = function(){
                box.innerHTML = '划出';
            }
    
            box.onmousedown = function(){
                box.innerHTML = '按下';
            }
    
            box.onmouseup = function(){
                box.innerHTML = '<h1>松开</h1>';
            }
    
    
            // 显示鼠标在 盒子中的坐标
            // event对象: 包含鼠标, 键盘的操作
            //  
            //     event对象.offsetX  鼠标相对于当前元素的横坐标
            //     event对象.offsetY  鼠标相对于当前元素的纵坐标
            // 
    
            box.onmousemove = function(en){
                // 兼容event对象
                var en = en || window.event;
    
                // box.innerHTML = 'x:  '+en.offsetX+'   y:   '+en.offsetY;
                box.innerHTML = 'x:  '+en.x+'   y:   '+en.y;
                // box.innerHTML = 'x:  '+en.clientX+'   y:   '+en.clientY;
                // box.innerHTML = 'x:  '+en.screenX+'   y:   '+en.screenY;
            } 

# 键盘事件
    1. 键盘事件
        onkeydown       某按键被 按下
        onkeyup         某按键被 松开
        onkeypress      某按键被 按下, 直到松开

        注: 
         * 打印键: 数字, 字母, 标点推荐用 press
         * 功能键: ctrl, f1, pageup等推荐用 down 或 up

    2. event对象
        event.key       按键的标识符   (key)
        event.keyCode   按键的ASCII码
        event.which     按键的ASCII码, 兼容写法

        event.altKey    检测alt是否被按下, 如果按下返回true, 否则返回false
        event.ctrlKey   检测ctrl是否被按下, 如果按下返回true, 否则返回false
        event.shiftKey  检测shift是否被按下, 如果按下返回true, 否则返回false
        event.metaKey   检测开始菜单键是否被按下, 如果按下返回true, 否则返回false

# 正则
    1. 格式
		/正则表达式/修饰符 

		注
		 * 正则被 一对/ / 包住
		 * 修饰符 不是必需品, 可以写可不写
	
	2. 正则匹配
		对象.search()     搜索并返回索引,  搜索失败则返回: -1
		对象.replace()    搜索并替换, 返回替换完的对象, 搜索失败则原样返回对象
		对象.match()      搜索并返回被搜索到的结果. 搜索失败则返回: null
    
    3. 原子
		在正则中, 所有字符都认为是一个原子. 原子是正则中的最小单位
		例如: 
			abc  3个原子
			156  3个原子, 不是整数156
	
	4. 中括号
		[]      匹配[]之内的任意一个原子
		[^]     匹配[]之外的任意一个原子

		[0123456789]    匹配任意一个数字
		[0-9]            匹配0-9 之间的任意一个数字
		[0-38-9]         匹配0-3 和 8-9 之间的任意一个数字

		[a-z]            匹配任意一个小写字母
		[a-cm-nx-z]      匹配a-c 和 m-n 和 x-z 之间的任意一个字母

		[A-Z]            匹配任意一个大写字母
		[A-CX-Z]         匹配A-C 和 X-Z 之间的任意一个字母

		/[A-Z]/i         匹配任意一个字母且不区分大小写
		[a-zA-Z]         匹配任意一个字母且不区分大小写

		[a-zA-Z0-9]      匹配任意一个数字or字母 且 不区分大小写

		[\u4e00-\u9fa5]  汉字范围: \u4e00 ~ \u9fa5


		注:
		 * - 范围都是参考: ASCII码  
    
    5. 竖线
		正则1|正则2|正则3|...
		
		匹配的是竖线 侧边的一个整体
		
	6. 集合
		\d      匹配任意一个数字, 相当于[0-9]
		\s      匹配任意一个不可见原子, 相当于[ \n\r\t]
		\w      相当于 [0-9a-zA-Z_]

        \D      全部与小写相反 [^0-9]
        \S      全部与小写相反 [^ \n\t\r]  所有可见原子
        \W      全部与小写相反 [^0-9a-zA-Z_]

        .       小数点, 能匹配除 \n 以外的任意一个原子
    
    7. 量词
        a{n}    原子a 正好连续出现n次
        a{n,}    原子a 正好连续至少n次
        a{n,m}    原子a 正好连续至少n次, 至多m次 

        a+      原子a 至少出现1次
        a?      原子a 至少出现0次, 至多出现1次
        a*      原子a 至少出现0次
    
    8. 小括号
        ( )     将结果存入结果集
        (?: )   不会将结果存入结果集, 只是单纯当做一个整体

        作用1: 将 () 内的原子当成一个整体, 可当做一个大原子
        作用2: 捕获子模式
        作用3: (?: ) 取消子模式

        后向引用: 
         后面引用前面的, 以保证两处的值一模一样的

         格式: \索引

        例如: 
            \1 : \1 和 第一个() 匹配到的值是 一模一样
            \2 : \2 和 第二个() 匹配到的值是 一模一样
    
    9. 预查模式
        (?= ) 正向预查
        (?! ) 反向预查 (不是从后往前, 而是 ?= 取反)
        
    10. 边界
        ^a   以原子a 开头
        a$   以原子a 结尾
        
# window
    1. BOM
        浏览器对象模型 ( Brower Object Model )
        能直接与 浏览器进行交互

    2. window
        几乎所有浏览器都支持window
        window 代表: 浏览器窗口, 所以全局可用的变量, 函数等都属于window对象
        
    3. 浏览器尺寸
        标准写法
        window.innerWidth   浏览器当前可视窗口的宽度(包含滚动条, 不包含任务栏,控制台,标签页)
        window.innerHeight  浏览器当前可视窗口的高度(包含滚动条, 不包含任务栏,控制台,标签页)

        IE写法
        document.documentElement.clientWidth    同上
        document.documentElement.clientHeight   同上

        注: 
         * 以上写法只能获取第一页的宽高
    
        兼容获取
        document.body.clientWidth
        document.body.clientHeight
        
        通用写法
        var width = window.innerWidth ||  document.documentElement.clientWidth || document.body.clientWidth
    
    4. 窗口操作
        window.open()
        window.close()
        
    5. 弹窗
        window.alert()      提示框, 返回值: undefined
        window.prompt()     输入框, 返回值: 输入的数据
        window.confirm()    确认框, 返回值: boolean值
    
    6. 滚动条
        获取当前滚动条距离顶部的距离
        通用写法: document.documentElement.scrollTop
        其他写法: document.body.scrollTop

    
        window.scrollBy()   相对于当前位置进行滚动
        window.scrollTo()   滚动到指定位置(不需要考虑当前位置)
    
# other-BOM
    1. navigator
        包含浏览器的用户信息, 终端, 版本等信息 
        navigator.userAgent
    
    2. screen
        包含客户端的屏幕信息

        screen.width        显示屏幕宽度(包含任务栏)
        screen.height       显示屏幕高度(包含任务栏)
        screen.availWidth   显示屏幕宽度(不包含任务栏)
        screen.availHeight  显示屏幕高度(不包含任务栏)
        
    3. history
        包含当前网页的前后历史记录
    
    4. location 
        包含的当前URL信息

        location.assign()    跳转到指定地址 (会产生记录)
        location.replace()   将当前网页替换成指定地址内容( 不会产生上一条记录)
        location.reload()    重载(刷新)
                             true:  从服务器里面读取
                             false: 从缓存里面读取

# document 
    1. DOM
        文档对象模型: Document Object Model
        将HTML中的每一个元素都当做一个节点

        * 文档节点: document
        * 元素节点(标签): element
        * 属性节点: attribute
        * 文本节点: text
    
    2. Document
        document对象属性
            document.all
            document.body
            document.title

        document对象方法
            document.createElement()       创建元素(标签)
            document.createAttribute()     创建属性
            document.createTextNode()      创建文本
    
    
                        window
                           |
       navigator  location  document history screen 
                            |
                          html
                            |
                  head              body
                    |                |
             meta  link       a    div   p   h1 ...
             
    <button onclick="demo()">创建一个p标签</button>
    <script>
        
        console.log( document.all );

        document.title = '666'; //给title命名

        function demo(){
            // 创建节点
            var a = document.createElement('p');
            var b = document.createTextNode("CLICK ME");
            var c = document.createAttribute('class');
            // c.value = "xxx";

            // 设置相关的值
            a.setAttributeNode(c); //把c名字设置给a标签
            a.appendChild(b); //把b内容添加到a标签

            // 显示到 body里面
            document.body.appendChild(a);

            console.log( document.doctype );
        }

# 节点
    2. document 
            document 对象是 HTML 文档的根节点

            document对象集合
                document.all    获取document中所有的html元素
                document.forms  获取document中所有的form元素
                document.images 获取document中所有的img元素
                document.links  获取document中所有的form元素

            document对象属性
                document.body       返回整个body体
                document.domain     返回当前域名
                document.title      返回当前网页标题
                document.URL        返回当前url地址
                document.documentElement    返回文档的根节点  

            document对象方法
                document.getElementById()           根据id获取element对象
                document.getElementsByClassName()   根据class获取element对象
                document.getElementsByTagName()     根据标签名获取element对象
                document.getElementsByName()        根据name获取element对象
                document.write()                    写入html元素 

                document.createElement()            创建元素节点
                document.createAttribute()          创建属性节点
                document.createTextNode()           创建文本节点

        3. element
            所有的标签元素都是element

            属性
                节点.childNodes       获取该节点的所有子节点 (包含文本, 元素节点)
                节点.firstChild       获取该节点的第一个子节点
                节点.lastChild        获取该节点的最后一个子节点
                节点.nextSibling      获取该节点的下一个兄弟节点
                节点.previousSibling  获取该节点的上一个兄弟节点
                节点.parentNode       获取该节点的父级节点


                节点.children                获取该节点的所有子元素节点
                节点.nextElementSibling      获取该节点的下一个兄弟元素节点
                节点.previousElementSibling  获取该节点的上一个兄弟元素节点


                节点.tagName         获取/设置该节点的标签名 
                节点.id              获取/设置该节点的id名 
                节点.classList       获取/设置该节点的class名 (集合)
                节点.className       获取/设置该节点的class名 (字符串)


                节点.innerHTML       获取/设置该节点的文本内容(包含标签, 包含空格)
                节点.textContent     获取/设置该节点的文本内容(不包含标签, 包含空格)
                节点.innerText       获取/设置该节点的文本内容(不包含标签, 不包含空格)


                节点.clientWidth     获取该节点的宽度  (width+padding, 不包含border,滚动条)
                节点.clientHeight    获取该节点的高度  (height+padding, 不包含border,滚动条)
                节点.offsetWidth     获取该节点的宽度  (width+padding+border)
                节点.offsetHeight    获取该节点的高度  (height+padding+border)


                节点.scrollWidth     获取该节点的滚动区间宽度  (不包含滚动条)
                节点.scrollHeight    获取该节点的滚动区间高度  (不包含滚动条)
                节点.scrollLeft       获取该节点滚动条距离最左侧的距离
                节点.scrollTop        获取该节点滚动条距离最顶部的距离


                节点.nodeName        获取该节点的名字
                节点.nodeType        获取该节点的类型
                节点.nodeValue       获取该节点的值
                
            属性
            // 1. 获取所有的form集合
                console.log( document.forms );

            // 2. 获取所有的图片
                console.log( document.images );

            // 3. 获取所有的链接
                console.log( document.links );

            // 4. 获取当前网页标题
                console.log( document.title );

            // 5. 给ul添加一个子元素li, li的文本内容: 不知火舞
                var A = document.getElementById('A');
                var x1 = document.createElement('li');  // 创建了一个元素节点

                // 添加内容1
                x1.innerHTML = '不知火舞';

                // 添加内容2
                // var x2 = document.createTextNode('不知火舞');
                // x1.appendChild(x2);

                A.appendChild(x1);

            // 6. 仅仅获取ul的所有子元素节点
                console.log( A.children );
                console.log( A.children.length );
                console.log( A.children[0] );

            // 7. 获取ul的所有子节点
                console.log( A.childNodes );

            // 8. 获取悟空的前面一个兄弟元素节点
                var B = document.getElementById('B');
                console.log( B.previousElementSibling );

            // 9. 获取悟空的前面一个兄弟节点
                console.log( B.previousSibling );

            // 10. 获取悟空后面一个兄弟元素节点
                console.log( B.nextElementSibling );

            // 11. 获取悟空后面一个兄弟节点
                console.log( B.nextSibling );

            // 12. 获取悟空的父级节点
                console.log( B.parentNode );

            // 13. 获取box的节点name, 节点value, 节点type
                var box = document.getElementById('box');

                 nodeName
                  元素: 标签名
                  属性: 属性名
                  文本: #text
                  注释: #coment
                  文档: #document
                  文档声明: html

                 nodeValue:
                  元素: null
                  属性: 属性值
                  文本: 正文内容
                  注释: 注释内容
                  文档: null
                  文档声明: null
                
                 nodeType:
                  元素: 1
                  属性: 2
                  文本: 3 
                  注释: 8
                  文档: 9
                  文档声明: 10
                
                
                // 元素节点的name, value, type
                console.log( box.nodeName );
                console.log( box.nodeValue );
                console.log( box.nodeType );

                // 文本节点的name, value, type 
                console.log( box.firstChild );
                console.log( box.firstChild.nodeName );
                console.log( box.firstChild.nodeValue );
                console.log( box.firstChild.nodeType );

                // 注释节点的name, value, type 
                console.log( box.lastChild );
                console.log( box.lastChild.nodeName );
                console.log( box.lastChild.nodeValue );
                console.log( box.lastChild.nodeType );

                // 文档节点的name, value, type
                console.log( document.nodeName);
                console.log( document.nodeValue);
                console.log( document.nodeType);

                // 文档声明的name, value, type
                console.log( document.documentElement.previousSibling.nodeName );
                console.log( document.documentElement.previousSibling.nodeValue );
                console.log( document.documentElement.previousSibling.nodeType );

            // 14. 获取ol的标签名
                console.log( A.tagName );

            // 15. 获取ol的id
                console.log( A.id );

            // 16. 获取ol的class
                console.log( A.className );  // class 字符串
                // A.className = 'x';
                console.log( A.classList );  // class 集合
                // A.className = 'x';
            
            // 17. 获取ol的文本内容
                console.log( A.innerHTML ); // 包含空格, 标签
                console.log( A.innerText ); // 只获取文本(不包含空格, 不包含标签)
                console.log( A.textContent ); // 不包含标签, 包含空格和文本

            // 18. 获取box的宽度, 高度
                var box = document.getElementById('box');

                // width + padding  (不包含滚动条)
                console.log( box.clientWidth, box.clientHeight);

                // width + padding + border
                console.log( box.offsetWidth, box.offsetHeight);


            // 19. 获取box的滚动内容的宽度, 高度
                box.onscroll = function (){
                    console.log( box.scrollLeft );  // 距离box滚动条最左面的距离
                    console.log( box.scrollTop );   // 距离box滚动条最上面的距离
                }
                console.log('------------- 分隔符 --------------');
            

            方法
                节点.hasChildNodes()          是否有子节点
                节点.appendChild()            追加一个子元素
                节点.insertBefore(new,node)   插入一个子元素(在指定节点前插入一个新节点)
                节点.replaceChild(new,old)    替换一个子元素
                节点.removeChild()            删除一个子元素

                节点.hasAttribute()           是否有指定属性名
                节点.hasAttributes()          是否有属性 (不需要指定具体属性, 只要有任意一个属性即可)
                节点.getAttribute()           查看属性
                节点.setAttribute(属性名, 属性值) 设置属性
                节点.removeAttribute()        删除属性

                节点.getAttributeNode()       查看属性节点
                节点.setAttributeNode()       设置属性节点
                节点.removeAttributeNode()    删除属性节点

                节点.cloneNode()              克隆节点 (true: 连同子节点一起克隆.   false: 仅克隆当前节点的本身)
            
                节点.addEventListener()       添加监听
                节点.removeEventListener()    移除监听

         方法
            // 1. 查看ol 是否有子节点
                console.log( A.hasChildNodes() );

                var p = document.getElementsByTagName('p');
                console.log(  p[0].hasChildNodes() );

            // 2. 追加一个子元素
                var x2 = document.createElement('b');
                x2.innerHTML = '加粗标签'
                box.appendChild(x2);


            // 3. 插入一个子元素
                var x3 = document.createElement('b');
                x3.innerHTML = '加粗标签'
                box.insertBefore(x3, box.childNodes[1]);

            // 4. 替换一个子元素
                // var x4=  document.createElement('li');
                // x4.innerHTML = '八戒';

                // A.replaceChild(x4, B);

            // 5. 删除一个子元素
                A.removeChild(B);


            // 6. 查询属性
                console.log( A.getAttribute('id') );

            // 7. 查询属性节点
                console.log( A.getAttributeNode('id') );


            // 8. 设置属性
                A.setAttribute('abc', '666') 
                A.setAttribute('title', '999') 


            // 9. 设置属性节点
                var x5 = document.createAttribute('xyz');
                x5.value = '000';

                A.setAttributeNode(x5)

            // 10. 克隆节点
                // document.body.appendChild(   A.cloneNode(true)    ) 
                document.body.appendChild(   A.cloneNode(false)  