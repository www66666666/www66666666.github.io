<font style="font-size:1.3em;font-weight:bold;"> 目录 </font> 
[toc]

# PHP是什么
    PHP术语:超文本预处理器
    HTML术语:超文本标记语言
    CSS术语:层叠样式表
    
    一句话:一种用来开发 动态网站的服务器脚本语言
    
## PHP文件存储位置
    服务器根目录: wamp/www目录
    
    wampserver环境的根目录: www
    phpstudy环境的根目录: www
    XAMPP环境的根目录: htdocs
    apache原生环境的根目录:htdocs
    
    注意:
        根目录下可以创建子目录和php文件,但是目录名不能
    含有任何中文和 / | \ * ? " < > :
    
## 如何运行PHP文件
    * 打开集成环境 ( wamp, phpstudy, xampp, apache 等 )
    * 打开浏览器
    * 地址栏输入: localhost   即可访问www目录
     
    注意: 
        目录下含有 index文件, 那么当访问该目录时, 会自动执行index文件
        
## 定界符
    只有在定界符之内,才能识别PHP代码
    
    定界符格式: <?php    PHP代码    ?>
        <?php   开始定界符
        ?>      结束定界符 (若php文件里面是纯php代码,可省略结尾定界符)
        
## 输出内容
    格式: echo "内容";
    简化输出:<?= "内容" ?>  ==> <?php echo "内容" ?>
    
        条件限制:当定界符内,只需要一个echo时,可简化成上面的写法
        
## PHP设置编码
    格式: header('content-type:text/html;charset=编码')
        一般情况下,设置编码写在文档的最前面
## 注释
    单行注释: // 注释内容
    单行注释: #  注释内容
    多行注释: /* 注释内容 */
    
## 基本语法
    每一条PHP命令均以分号作为结束符
    最后一条PHP命令可以省略 结速符
    
## 查看PHP环境/信息/插件
    phpinfo()
    
# 定义变量
    1.定义:
        存储可以变化的量就是变量
        
    2.格式:
        $变量名 = 值
        
    3.命名规范:
        组成:由数字,字母和下划线组成不能以数字开头
              区分大小写
              变量名前必须加 $ 符
              
    4.未定义变量(报错)
        没有值的变量就是未定义变量
        
    5.内存划分
        每次生成一个变量,就需要申请一些内存空间
        每个内存空间,可以有一个变量或多个变量去引用(指向)
        
        垃圾回收机制:
            一个内存空间 一旦没有变量引用时,那么该内存空间会被认为是
        垃圾通过机制,自动删除没有变量引用的内存,从而达到释放内存的效果
        
    6.删除变量
        unset(变量)
        unset 就是删除变量与内存之间的引用意味着,被unset的变量
              都是没有值的,也就成了未定义变量
              
## 变量技巧
    1.可变变量
        将一个变量的值作为另一个变量的名来使用 ($$变量名)
        
    2.引用变量
        传值    $a = 10; $b = $a;($b = 10 传值)
        传址    传内存地址(引用变量)
                $b = &$a; (将$a的内存给了$b,$a和$b共用一个内存)
                
# 数值有8种类型
    标量类型 (基本)
        整形    int
        浮点型  float 小数
        布尔型  bool
        字符串  string 包含任意文字,标点
        
    复合类型
        数组    array
        对象    object
        
    特殊类型
        资源    resource
        空      null

# 整型 int  integer
    1.最大值
        PHP_INT_MAX 
        
        PHP5 及更早的最大值: 2147483647
        PHP7 的最大值: 9223372036854775807
    
    2.判断是否为int
        is_int( 变量 )
            返回值:是整型返回true,不是则返回false
        
        gettype(变量)   直接获取数据类型
        
    3.进制
                      基数范围     前缀
        二进制          0~1         0b
        八进制          0~7         0
        十进制          0~9         无
        十六进制      0~9 a~f       0x
        
        任意进制 -> 十进制
        公式: 基数*进制^次方

        个位次方: 0
        十位次方: 1
        百位次方: 2
        千位次方: 3
        以此类推...
    
        十进制 -> 任意进制
        算法: 
            将十进制 除以进制 (除到1), 结果倒取 余数

# 4种输出的区别
    1.echo  (正式项目)
        支持int, float, string, resource
        语法结构
    
    2.print (少用,最好别用)
        支持int, float, string, resource
        语法结构
        
    3.print_r   (输出大量数组)
        支持int, float, string, array, object, resource
        函数
        array输出个数理论上限(只要内存够用)
    
    4.var_dump  (平时测试)
        支持int, float, string, bool, array, object,resource, null
        函数
        array输出顶多 128个(有上限)
        输出的内容比较全面(文件地址, 行号, 类型, 值, 长度)
# 浮点型 float  小数
    1.科学计数法 
        xEy = x * 10的y次方
        
    2.超过PHP_INT_MAX 时,自动转为浮点型
    
    3.检测是否为浮点型
        is_float()
    
    4.有效位数
        从前向后,第一个非0数字开始,向后保留14位
        
    5.浮点等值比较
        == 比较两边是否相等
        
        不要使用浮点等值比较
        原因: 由于电脑都是 二进制电脑,所有的操作最终都会转为二进制
        浮点数的二进制相对不稳定,导致最终结果有点微差
        
# 布尔型 bool   boolean
    1.值的写法
        true    对/好/是/正确/可行...
        false   错/坏/否/错误/不行...
        
        布尔值代表两种 极端对立状态
        
    2.作用
        在比较,判断时使用较多
        
    3.等值
        有以下7种情况与false等价,其余都与true等价
        * false
        * 0
        * 0.0
        * null  空
        * []    空数组
        * '' 或 '0'  (不区分单双引号)
        * 未定义变量
        
    4.检测是否为 布尔型
        is_bool()

# 字符串
    1.值的写法
        单引号
        双引号
        heredoc结构
    
    2.值的长度
        最大的长度: 2G
        
    3.检测是否为字符串: is_string()
      检测是否为标量: is_scalar()
      检测是否为数字or数字字符串: is_numeric()
            数字: int 或 float
            数字字符串: 纯数字的字符串 or 科学计数法
            
    4.单双引号的区别 (面试题)
       单引号:  (推荐)
                不解析变量
                速度快
                不解析转义字符  解析转义转义字符
                
        双引号:
                解析变量(建议给变量加{},能提供更好的变量边界解析)
                速度慢
                解析转义字符    解析转义转义字符
        
        转义字符
            转移符号: \ 具有将普通字符串变成特殊字符,也能将特殊字符变成普通字符
            
            天生就是特殊字符: ' " $ \ ...
            
            转义 转义字符
            \'  \"  \$  \\
            
            转义字符
            \n 换行
            \r 回车
            \t 制表符,tab
            ...
    
    5.单双引号的共同点
      单双引号可以互插,不能自插
      
    6. heredoc结构 可以插入 单双引号

# 数组 array    (简单介绍)
    1.定义
        容器,能够存放各种数值的容器
        数值都是由 键值对 组成
        
    2.格式
        $变量[] = 值
        $变量 = [值1,值2,值3...]
        
    3.数组基本操作
        查看数组中的一个值: 通过 已存在的键 来查
        修改数组中的一个值: 通过 已存在的键 来修改
        新增数组中的一个值: 通过 不存在的键 来新增
        删除数组中的一个值: 通过 已存在的键 来删除
        
    4.检测是否为数组
        is_array()

# 对象 (略讲)
    1.生成一个对象
        $变量 = new stdClass;
    
    2.检测是否为对象
        is_object()
        
# 资源 (略讲)
    1.生成一个资源
        $变量 = fopen('文件地址', 'r')
        
    2.检测是否为资源
        is_resource()

# 空    null
    1.作用: 占位
      目的: 为了后面直接使用内存,而不需要当场申请内存
      
    2.检测是否为 null
        is_null()
        
    3.有3种情况,变量值直接显示为null
        1.主动赋予 null
        2.未定义变量
        3.被删除的变量  (被删除的变量就是未定义变量)
        
# 自动类型转换
    强类型语言: 不支持隐式转换
    弱类型语言: 支持隐式转换
    
    隐式转换: 偷偷摸摸的把数据类型转成其他类型
    
    bool
        true => 1 或 1.0
        false => 1 或 0.0
    
    string
        保留第一个非数字之前的所有数字(非数字不包含. 和 e)
        抛弃第一个非数字 和 非数字之后的所有内容
    
![join](https://note.youdao.com/yws/public/resource/bcd74097c9c19078fc7b2e45d1a2af9c/xmlnote/WEBRESOURCE6f74ee8a74fa84e1d4abfb36baf6827b/4248)

# 强制类型转换
    1.临时转换
        1.通过运算符 来转换类型
            var_dump( (bool)$str );
        2.通过 函数 来转换类型
            var_dump( boolval($str)  )
    2.永久转换
        通过 函数 来转换类型
             settype($str, 'int');
             var_dump($str);

# 常量
    1.定义:
        当值 恒定不变时,该变量即可称之为常量
        
    2.格式1:
        const 常量名 = 常量值
        
      格式2:
        define(常量名, 常量值 [,bool值])
                            false:区分大小写,默认
                            true:不区分大小写
                            
    3.注意点:
        不需要 $ 符修饰
        区分大小写 (推荐大写)
        常量不能重新赋值
        常量不能重新定义
        
    4.预定义常量
        PHP_INT_MAX     最大整形
        PHP_VERSION     PHP版本
        PHP_OS          PHP当前所在的操作系统
        M_PI            圆周率
        
        预定义? : 就是PHP解释器内置的常量,不需要我们自己定义
        
    5.魔术常量
        __FILE__    获取当前的盘符路径
        __DIR__     获取当前的目录
        __LINE__    获取当前代码的所在行数
        
# 算数运算符
![join](https://note.youdao.com/yws/public/resource/bcd74097c9c19078fc7b2e45d1a2af9c/xmlnote/WEBRESOURCEd864f4d804c38a1d56a5f1e37ea97f72/4252)

    +  -  *  /     %取模 求余数

    取模 
        1.取模结果的正负问题
          结果的正负 取决于第一位数的正负
          
        2.取模结果的范围问题
           余数限制到 0 ~ x ,被取模数为x+1
           任意数 % x 的结果范围必然是: 0~x-1
            
          最终公式:
            x ~ y 之间的范围
            任意数 % (y-x+1)+x
            
          %2 的余数 = 1 则证明是 奇数
                    = 0 则证明是 偶数
                    
          %3 的余数 = 0 则证明是 3的倍数
          
    小结: 
         %10         保留最后1位数
         %100        保留最后2位数
         %1000       保留最后3位数
         依次类推
         
         /10         去掉最后1位数, 保留剩余位数
         /100        去掉最后2位数, 保留剩余位数
         /1000       去掉最后3位数, 保留剩余位数
         依次类推

    拼接符  . 
    作用: 拼接字符串与变量 or  变量与变量
   
# 赋值运算符 equal
    =       =的左边 只能是变量, =的右边只能是 数值或运算
              先算= 的右边, 再算=的左边
              
    +=      a += 5  =>  a = a + 5
    -=      
    *=      
    /=      
    %=  
    .=      a .= 5  =>  a = a . 5
    
# 比较运算
    比较运算符的结果只有: true 或 false
    >
    >=
    <
    <=
    ==      判断两边的值是否相同
    ===     全等: 判断两边的值是否相等 且 数据类型也相等
    !=      判断两边的值是否不等
    !==     不全等: 只有全等时为false,其余都是true
    
    字符串与字符串比较时,是基于 ASCII 比较
    0 => 48
    A => 65
    a =>97
    字典排序法 比较
    数字字符串比较时,看自然数
    数字 + 字母 字典排序法

# 递增递减
    ++      自己给自己+1
    --      自己给自己-1
    $a++    先返回$a, 再给$a+1
    ++$a    先给$a+1, 在返回$a
   
# 逻辑运算符
    结果只有 true 或 false
    
    逻辑与  &&      两边为真即为真,一边为假即为假
    逻辑或  ||      一边为真即为真,两边为假即为假
    逻辑非  !       真亦假,假亦真
    
    纯逻辑运算时,优先 ! > && ||
    
# 三元运算
    一元运算符
        ++ -- !
    二元运算符
        + - * / ...
    三元原运算符
        ? :
    格式:
        条件表达式 ? true环境 : false环境
        
    运算股则:
        条件成立,则执行true环境代码
        条件不成立,则执行false环境代码
        
    小结:
        简单判断:用三元
        复杂判断:用分支
        
    逻辑运算符
    and 逻辑与 &&
    or  逻辑或 ||
    
    and 和 or 优先级比 = 还要低
    &&  和 || 优先级比 = 还要高
    
# 三个常用函数
    1.unset()
        删除一个变量
        返回值:无
        
    2.empty()
        检测一个变量是否为空 (检测一个变量是否与false等价)
        返回值: 无
        
    3.isset()
        检测一个变量是否设置(检测一个变量是否不为 null)
        返回值:bool
        
# 流程控制
    1.顺序结构: 代码从上往下依次执行
    2.分支结构: 通过if/switch 来进行分支选择,仅能选择一条分支
    3.循环结构: 通过for/while 来不断的重复某一段代码
    
    代码块: 可以是1行, 2行, n多行代码,甚至是0行代码
    所有if (条件表达式)
    
    if分支1
    if()代码块
    影响范围: 只有紧跟在后面的一句话
    
    if分支2
    if(){代码块}
    
    if分支3
    if(){
        代码块1
    }else{
        代码块2
    }
    
    if分支4
    if(){
        代码块1
    }elseif{
        代码块2
    }...
    
    if分支5 (巢状分枝)
    if(){
        if(){
            if(){
                if(){
                    
                }else{
                    
                }
            }else{
                
            }
        }else{
            
        }    
    }else{
        
    }
    
    注意: 在定值条件下,switch的效率比 if 高
          在范围条件下,只能选择if
          
# for循环
    循环三要素: 初始化, 循环条件, 循环增量
    
    for( 1.初始值; 2.循环条件; 3.循环增量 ){
            4.代码块
    } 
    循环顺序: 1 243 243 243 ...
              1 2
              一旦 2.循环条件 不成立时,则立马结束循环
    
    循环条件: "最终结果"是否与true等价, 若等价, 则条件成立, 否则条件不成立
    循环增量: 不只是可以做++, --, 还可以做+, -, *, /, %, &&, || 等等任意运算
    
    注: 当循环条件什么也没写时, 则无限循环(死循环)      
# while循环
    1.初始值
    while( 2.循环条件 ){
        3.代码块,含有循环增量
    }
    一旦循环条件不成立,则立马结束循环
    
    1.初始值
    do{
        2.代码块;含有循环增量
    }while( 3.循环条件 );
    
    while 和 do while 的区别?
        while 先判断循环条件在运行代码块
        do while 先运行代码块在判断循环条件

# 流程控制符
    1.continue  立马结束当前一轮循环,准备进入下一轮循环
    2.break     立马结束 switch 或循环
    3.die/die() 立马结束程序
      exit/exit()
      
# 循环与HTML混合使用
    for 与 html 混合使用
    
        <?php  for( ; ; ):  ?>
            html 原生代码
        <?php   endfor   ?>
     ---------------------------------   
    if与html混合使用
        <?php   if( 条件 ):  ?>
            html 原生代码
        <?php    endif      ?>
        
        
        <?php   if( 条件 ):  ?>
            html 原生代码
        <?php    else:    ?>
            html原生代码
        <?php    endif    ?>
        
        
        <?php   if( 条件 ):  ?>
            html 原生代码
        <?php    else:    ?>
            html原生代码
        <?php    endif    ?>
        
# 函数 function
    1.定义
        用来执行特定的任务, 简称: 功能
    
    2.分类
        系统函数: 内置函数, 由php开发组所设计的一些函数,可以直接使用
        自定义函数: 根据项目的需求变化而变化
        
    3.自定义函数
        function 函数名([参数1, | 参数2=值2, ...])
        {
            代码块(功能)
        }
    
    4.特性
        * 函数
        * 定义函数的位置 和 调用函数的位置 没有先后顺序
        * 函数就算没有调用, 语法依旧正常解析
        * 函数互不影响, 却可以互相调用
        
    5.调用函数
        函数名()
        函数名( 参数 )

## 函数名命名
     1.命名规范: 由数字,字母,下划线组成,不能以数字开头,不能是关键字
     2.命名形式:
            驼峰式命名法:从第二个单词开始,首字母大写(小驼峰)
            帕斯卡命名法:每个单词的首字母都大写(大驼峰)
            匈利亚命名法:每个单词之间用 下划线 隔开
            
     3.函数名不区分到小写
     4.函数名不能重复
     5.函数名取得要有意义,目的提高可读性
        常见多单词: 动词+名词

## 返回值
     返回值 return
     1.位置: 只能写在函数的内部
     2.作用: 立马结束函数,将返回值带回到调用函数的地方
             若函数没有return,那么可以理解为默认返回null
             
     3.返回值的类型: 任意类型
     
     4. 如何一次性返回多个值
            将 多个值 存储在 一个数组里面, 并返回该数组
## 参数
     1.参数
        形式参数:简称"形参",在定义函数时给的参数  parameterparam
        实际参数:简称"实参",在调用函数时给的参数  argumentarg
        
     2.参数个数
        实参个数 = 形参个数     形参按照实参先来后到的顺序,依次接收
        实参个数 > 形参个数     形参按照实参先来后到的顺序,多余的实参直接抛弃
        实参个数 < 形参个数     PHP5:形参按照实参先来后到的顺序,依次接收
                                     多余的形参,默认为null
                                PHP7:直接报错,终止程序
                                
      3.参数默认值
            在定义函数时,给形参添加默认值
            参数默认值可有效解决"实参个数 < 形参个数" 的问题
            
      4.实参个数不确定时
        $a = func_get_args();   # 接收所有的实参， 以数组形式接收
        $b = func_get_arg( 2 ); # 接收数组实参中键为 2 的值
        $c = func_num_args();   # 获取实参的总个数
        var_dump($a, $b, $c);

# 自定函数的思路
    1.函数名
    2.参数
        *个数
        *默认值
    3.核心功能
        数据需要模拟
    4.补充数据
        死数据变成活数据
    5.返回值
        *是否需要有返回值
        *需要返回什么类型的返回值,要返回几个
    
# 全局变量
    作用域:
        全局变量:在函数外部声明的变量
        局部变量:在函数内部声明的变量
        
    特性:
        全局变量 不能直接在函数内部使用
        局部变量 不能直接在函数外部使用
        
    关键字: global
    位置: 只能写在函数内部
    在函数内部通过global声明局部变量,即可在外部使用
    
    超全局数组: $GLOBALS 存储所有全局可用的变量
    位置: 随便
        在函数内部通过 $GLOBALS[变量名] 即可使用
## 常量
     1.没有作用域,在函数外部声明常量,是可以直接在函数内部使用
     2.在函数内部,不能使用const关键字

## 静态变量
     理解为特殊的局部变量
     位置:在函数内部定义
     格式:static 静态变量名 = 值
     特性:
        普通的局部变量会随着函数的结束而结束
        *特殊的局部变量(静态)不会随着函数的结束而结束
        *当下一次再次强调此函数时,会直接使用上一次的静态值,不会再初始化
        
        多个函数内的同名静态变量,是互不影响
        
        可变函数:将一个变量的值作为一个函数名来使用
        引用函数:将一个实参的内存地址赋给形参

# 数组
    ## 28.数组
###    1.分类
        索引数组: 键为int
        关键数组: 键为string
        混合数组: 键既有int 又有string

###    2. 形式
        array
            键1 => 值1，
            键2 => 值2，
            。。。
            键N => 值N，

            
            键值对
            只要有一个键， 必然有一个值
            如果没有键， 必然没值

###    3. 键
        别称：下标， 索引， 偏移量
        键的类型： int 或 string

        * 键从未指定， 默认从0开始， 依次递增
        * 键部分指定， 空键会从"已有"的最大int键+1
        * 等价键
        *     纯数字 = '纯数字字符串'
        *     false = 0 = 0.0 = '0' = 0.x
        *     true = 1 = 1.0 = '1' = 1.x
        *     null = '' = 未定义变量
        * 非法键
        *     数组
        *     对象
        *     资源
        *
        * 键不能重复， 一旦重复， 后面的会覆盖前面的

###    4. 值
        * 值的类型： 任意类型

###    5. 格式
        $变量名[键] = 值
        $变量名 = [键1=>值1， 键2=>值2， 键3=>值4，  。。。  ]
## 29.多维数组
    多维数组： 数组中嵌套数组
###    一维
    array
        键 => 值
        
###    二维
    array
        键 => array

    array
        键1 => array1
        键2 => array2
        键3 => array3
    
###    三维
    array
        键 => array
                   键 => array   
## 30.遍历数组
###    1. 索引遍历
     索引遍历: 只能遍历有规律的数字键
         有规律的数字键 数组1
        $name =['百度','华为','阿里巴巴','腾讯','微软','谷歌'];
        var_dump($name);
        
        for ($i=0; $i <6 ; $i++) { 
            echo '<span style="margin-right:30px; color:#0ff;">'.$name[$i].'</span>';
        }
        echo '<hr>';
        
        有规律的数字键 数组2
        $name = [0=>'百度', 3=>'阿里巴巴', 6=>'腾讯', 9=>'华为'];
        for($i=0; $i<10; $i+=3){
            echo $name[$i].' ';
        }
        echo '<hr>';
###  2. 指针遍历
        指针遍历: 啥数组都能遍历, 固定从第一个键开始一直获取, 直到获取结束指针遍历
            无规律的数字键  数组3
            foreach(数组变量 as 键 => 值){
                        代码块
            }
        
            如果不需要键,则省略如下
            foreach(数组变量 as 值){
                    代码块
###   3.指针函数
    指针函数
    1.key()        获取当前指针所指向的键, 不会用完就自动指向下一个
    2.current()    获取当前指针所指向的值, 不会用完就自动指向下一个
    
    3.next()       将指针下移一位
                   超出范围, 键=null 值=false
    4.prev()       将指针上移一位

    5.reset()      将指针重置到第一位
                   超出范围, 返回false
    6.end()        将指针到重置最后一位

    7.each()       获取当前指针所指向的键和值, 且指针自动下移一位
                    each() 在PHP7 已弃用
## 31.字符串数组
    字符串数组
    字符串在一定意义上可以当做 索引数组来操作
    超出索引范围, 返回  空字符串
    
     数字, 字母, 标点占1个字节, 读取也是一个一个读取
     汉子占3个字节, 必须连续输出3个才能读取一个字(顺序不能随意颠倒)
     统计 字符串长度
        var_dump( strlen($str) );
## 32.预定义数组
    预定义数组
    $GLOBALS    超全局数组, 里面存储了所有全局可用的变量
    $_GET       接收所有以 get 方式传递过来的值
                  form中method=get
                  a链接的参数
                 
    $_POST      接收所有以 post 方式传递过来的值
                  form中method=post
    
    $_REQUEST   同时接收get, post 和 cookie

    $_FILES     专门用于接收上传的文件
                form表单的enctype = multipart/form-data
                form表单的method = post
                file表单的name必须要有值

                多文件有几个必要条件
                 file表单的 multiple 必须有
                 file表单的 name值后面必须要加[]

                
                file表单的name 值
                [abc] => Array
                    (
                        上传的文件名
                        [name] => 1.jpg

                        上传文件类型
                        [type] => image/jpeg

                        上传文件的临时文件
                        [tmp_name] => D:\wamp\tmp\php3F9E.tmp

                        上传的错误号: 0    没有错
                                      非0  有错
                        [error] => 0

                        上传的文件大小  单位: B 字节
                        [size] => 103498
                    )

    $_COOKIE    存储浏览器里面的cookie
    $_SESSION   存储服务器里面的session

    $_SERVER    含有了主机, IP, 参数, 脚本, 终端, 浏览器版本...
                HTTP_HOST   主机地址
                HTTP_USER_AGENT    终端, 浏览器版本
                HTTP_REFERER       上一级来源地址

                REMOTE_ADDR        客户端的IP地址
                REQUEST_METHOD     请求方式
                QUERY_STRING       请求参数
                REQUEST_URI        请求地址(含参数, 比较完整)

                SCRIPT_NAME        当前脚本地址( 根地址 )
                SCRIPT_FILENAME    当前脚本地址( 盘符地址 )
    
    
    
    echo 'GET方式: <br>';
    echo '<pre>';
    print_r($_GET);
    echo '</pre>';
    echo '<hr>';

    ?>
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>
        <!-- 
            action 值为空, 默认提交给当前页面
            method 值为空, 默认为get方式
        -->
        <form action="06-GET_POST.php" method="get">
            <input type="text" name="n1">
            <input type="submit">
        </form>
    
    
        <form action="06-GET_POST.php" method="post">
            <input type="text" name="n1">
            <input type="submit">
        </form>
        
    
        <form action="06-GET_POST.php?n2=999" method="post">
            <input type="text" name="n1">
            <input type="submit">
        </form>
    
        <!-- 
            method = get
            action 带参数
    
            默认情况: $_GET 接收表单值, 抛弃action参数
    
            如何让 $_GET既接收表单值, 又接收action参数
                将 action 参数作为 隐藏域传递过去
         -->
        <!-- <form action="06-GET_POST.php?n2=999" method="get"> -->
        <form action="06-GET_POST.php" method="get">
            <input type="text" name="n1">
            <input type="hidden" name="n2" value="999">
    
            <input type="submit">
        </form>
    
    
        <form action="06-GET_POST.php" method="post" enctype="multipart/form-data">
            <!-- 单文件 -->
            <!-- <input type="file" name="abc"> -->
    
            <!-- 多文件 -->
            <input type="file" name="abc[]" multiple>
            <input type="submit">
        </form>
         
    </body>
    </html>
## 33.explode 
    explode()    字符串 -> 数组
    implode()    数组 -> 字符串
    
    
    $str = 'a-b-c-d-e-f';
    $str = 'ab-cd-ef-';

    var_dump(explode('-', $str,0));
    var_dump(myExplode('-',$str,0));

    // 普通版的 exploded (必须会)
    function myExplode($exp,$str)
    {
        #初始化 空数组
        $arr = [];

        #在没有碰到 $exp之前的字符全部存储到$tmp中
        $tmp = '' ;

        #统计字符串的长度
        $len = strlen($str);

        for ($i=0; $i < $len ; $i++) { 
            echo $str[$i];
            if ($str[$i] !== $exp) {
                $tmp .= $str[$i];
            }else{
                $arr[] = $tmp;
                $tmp = '';
            }
        } 
        $arr[] = $tmp;

        return $arr;
 