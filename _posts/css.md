<font style="font-size:1.3em;font-weight:bold;"> 目录 </font> 
[toc]

# Css导入方式
    HTML 负责显示网页内容(文字, 图片, 音频, 视频...)
             专业术语: 超文本标记语言
             文件扩展名:   *.html

    Css  负责网页的美观 ( 整容师 )
             专业术语: 层叠样式表
             文件扩展名:   *.css
     
    Css 4种导入方式
        1. 外部样式表(正式项目常用, 推荐 )
            <link rel="stylesheet" href="css文件">

        2. 内部样式表(测试)
            <head>
                <style>
                    css代码
                </style>
            </head>

        3. 内联样式(能不用则不用)
            <开始标签 style="css代码" > 

        4. import导入
            <head>
                <style>
                    @import url('css文件地址');
                </style>
            </head>

            注意: @import 必须写在style里面的最前面


            import导入 和 外部样式表 的区别?
            * 外部样式表: 先加载css, 再加载HTML    
            * @import: 先加载HTML, 再加载css
                

# Css的基本语法
    1.css书写格式
        选择器{
            属性名:属性值;
            ...
            属性名:属性值;  (最后一个属性是可以省略分号)
        }
    2.css属性不区分大小写
      css选择器区分大小写
     
    3.css的注释
        /* 注释内容 */
# 基础选择器
## 1.html的四大通用属性
    style  给当前标签赋予css样式
    name   给当前标签取个大名 (重复)
    title  也是通用属性
    class  给当前标签取个绰号 (多个,重复)
    id     给当前标签赋予身份证号 (唯一)
## 2.基础选择器
     标签选择器
        格式
            标签名{
                属性名:属性值;
                ...
                属性名:属性值;
            }
        特性:
            影响极广,覆盖整个html
            适合做css初始化
            
      类选择器
        格式:
            .class名{
                属性名:属性值;
                ...
                属性名:属性值;
            }
        特性:
            一个标签可以有多个class名
            多个标签可以有相同class名
            多个class名只能用空格隔开
      身份选择器
        格式:
            #id名{
                属性名:属性值;
                ...
                属性名:属性值;
            }
        特性:
            一个标签不能有多个 id名
            多个标签在css中是可以用相同的id名,但是不推荐.
            因为在后期js中,id重名会报错的
## 3.关联选择器
    祖辈,后辈
    s1,s2,s3代表任意一基础选择器
    
    关联选择器写法
    s1   s2{...}  匹配s1的所有后辈元素s2
    s1 > s2{...}  匹配s1的所有儿子元素s2
    s1 + s2{...}  匹配s1后面的一个兄弟元素s2
    s1 ~ s2{...}  匹配s1后面的所有兄弟元素s2
    
## 4.组合选择器
    s1, s2, s3...{...}
    给不同的选择器赋予相同的样式
    且这些s1, s2, s3之间不需要有关系
    每个选择器之间用 逗号 隔开

## 5.伪类选择器
    1.hover
        s1:hover   {...}   当鼠标悬停在s1上时,触发css
        
    2.高阶hover
             (hover + 关联选择器)
        s1:hover   s2{...}  当鼠标悬停在s1上时,由后辈元素s2触发css
        s1:hover > s2{...}  当鼠标悬停在s1上时,由所有儿子元素s2触发css
        s1:hover + s2{...}  当鼠标悬停在s1上时,由后面一个兄弟元素s2触发css
        s1:hover ~ s2{...}  当鼠标悬停在s1上时,由所有兄弟元素s2触发css
        
    3.focus
        s1:focus{...}   当s1获取到光标时,触发css
        
    4.child
        父级 顺序 元素
        
        s1:first-child{...} 先找到s1的父级,再找到父级下的
            第一个子元素,最后看第一个子元素是不是s1元素
        
        s1:last-child{...}
        s1:nth-child(N){...}
        s1:nth-last-child(N){...}
        
    5.of-type
        父级 元素 顺序
        
        s1:first-of-type{...}先找到s1的父级,再找到父级下
            所有的s1元素,最后选择所有s1元素中的第一个
        
        s1:last-of-type{...}
        s1:nth-of-type(N){...}
        s1:nth-last-of-type(N){...}
        
        N 的写法
            * 数字
            * 单词    
            *   odd     奇数
            *   even    偶数
            * 公式
## 6.伪对象选择器
    s1::before{...} 匹配s1里面的最前面
    s1::after{...}  匹配s1里面的最后面
    
    before 和 after配合content属性使用
    作用: 在后期css浮动技术 配合使用
## 7.属性选择器
    选择器[属性名]{ ... }         含有该属性
    选择器[属性名=值]{ ... }      属性必须等于 指定值
    选择器[属性名~=值]{ ... }     属性值包含完整的值, 常用于class
    选择器[属性名*=值]{ ... }     属性值包含一个字符 值即可
    选择器[属性名^=值]{ ... }     属性值以 指定值开头
    选择器[属性名$=值]{ ... }     属性值以 指定值结尾
    
# 优先级
    选择器优先级规则: 
        权重相同时, 就近原则, 选择器离标签越近, 优先级越高
        权重不同时, 权重越高, 优先级越高

        内联样式 > ID选择器 > class选择器 > 标签选择器

    权重叠加
        id的权重: 100
        class的权重: 10
        标签的权重: 1
        (以上权重数字只是帮助我们分辨优先级高低, 并不是实际存在的)
        
        选择器分组无法叠加

    最高权重
        !important  
        位置: 写在属性值的后面, 分号前面

    继承性
        绝大多数后辈 是可以继承祖辈的属性
        小部分无法继承
        例如: a标签的颜色color
              h标签的大小font-size
            
              辨别方式: 打开调试器F12
                        选择你要查看的标签
                        查看css中的 Inheritied from xxx
                        是否有属性被 删除 (如果删除, 则代表无法继承)

              解决方案: 单独为该标签设置属性

# 字体颜色
    color: 单词 
            单词    red yellow blue green black white purple 
                    orange pink skyblue lightgreen
                    
            HEX     十六进制  范围:0~9 a~f  
                    #rrggbb
                    #rgb    当颜色两两相同时,可简写成rgb格式
            
            RGB     rgb 的范围: 0~255 或 %
            RGBA    a透明度: 0~1 可小数 0完全透明 1完全不透明
            
            HSL     H:色调 0~360  S:饱和度 %    L:亮度%
            HSLA    A:透明度  0~1可小数
            
    opacity: 0~1 透明度
# 长度单位
    像素px    px 随着电脑的分辨率变化而变化
    百分比    %  需要有一定的参照物(通常是父级)
    倍数      em 随着字体大小变化而变化

# 字体  
    字体大小 font-size:  % px
    字体家族 font-family:
    字体加粗 font-weight: bold  normal
    字体倾斜 font-style: italic normal
    字体行高 line-height: px
    
    简写:
        font: size family;      最基本的写法
        font: weight style size/line-height family
        
        weight 和 style 可以省略
        weight 和 style 相互交换位置
        line-height 必须写在 size的后面,中间必须用/隔开
        size 和 family的位置是固定的
        
    注意:
        * font-size 每个浏览器都有默认大小,建议至少要达到最大下限值
        * font-family 可写多个字体,从前到后依次识别
        * line-height 与当前标签的height一致时,可达到垂直居中
            的效果(仅限于一行文字)
        * 一旦使用简写,那么该标签之前的详细写法会全部覆盖(默认值)
 
# 背景
    详写:
        背景颜色: background-coloe:
        背景图片: background-image: url(图片地址)
        背景重复: background-repeat:
        背景大小: background-position: XY
                    x,y为正数时:背景图片向右or向下移动
                    x,y为负数时:背景图片向左or向上移动
    
    简写:
    background: [color] | [image] | [repeat] | [position/[size]]

# 边框
    1.单边边框
     详写:
        border-方向-属性:
     简写:
        border-方向:[width] | [color] | style
        
    2.四边边框
     详细:
        border-属性:
     简写:
        border: [width] | [color] | style
    
    3.圆角
     详写:
        border-上下-左右-radius: % px
     简写:
        border-radius: %  px
        
        px和%最大值的效果有所不同,具体看效果
    
    4.边框合并
        border-collapse:collapse
    
    5.外轮廓
        outline: none
        详写与简写与border基本一致

# 盒子阴影
    text-shadow: 水平位移  垂直位移  模糊度  阴影颜色;
    box-shadow: 水平位移  垂直位移  模糊度  [阴影面积]  阴影颜色 [内阴影];
    <!--box-shadow: 0px 15px 30px 0px rgba(0,0,0,0.1) inset;-->
    
    模糊度: 不能为负数, 最小值为0, 值越大越模糊
    阴影面积: 默认0px, 可以为负数, 值越大阴影面积越大
    内阴影: inset

# 鼠标样式
    cursor: none    隐藏鼠标
            pointer 手掌
            move    坐标
            wait    等待圆圈
            text    文本形式 大写I
            default 默认箭头
# 列表
    list-style: none    常用:取消项目符号
    
# 溢出
    溢出:超出标签范围之外的内容
    
    详写:
        overflow-x: hidden | visible | auto
        overflow-y: hidden | visible | auto
    简写:
        overflow: hidden | visible | auto
        
    当标签高度指定时,内容如果塞不下,就会自动切换到下一行
    如果需要强制变为一行,可通过属性white-space:nowrap;
    white-space: nowrap;  /*  强制转为一行 */
    overflow: hidden;     /*  将超出的部分进行隐藏  */
    text-overflow: ellipsis;   /* 将超出的部分用 ... 代替 */

# 文本
    text-indent: 首行缩进
            -decoration: 文本划线   none  underline 
            -overflow: 文本溢出     ellipsis
            -shadow: 文字阴影       
            -align: 文本水平对齐方式    left center right

        vertical-align: 垂直对齐方式    top  middle  bottom


        坑: 
            vertical-align 默认对外对齐
            如果需要对内对齐, 需要将当前元素转为 td单元格才行(display: table-cell;)
# 内联/块级元素
    块级元素 block
    最具有代表性的标签: div
    * 独占一行
    * 宽度默认与浏览器一致
    * 高度默认与内容高度一致 (由内容撑开的)
    * 宽,高,行高,内边距,外边距全部可以手动控制
    * 容纳性:任何元素
    
    行级元素,内联元素 inline
    最具有代表性的标签: span
    * 同在一行
    * 宽度默认都与内容长度一致
    * 高度默认都与内容高度一致
    * 宽,高,上下边距无法控制
    * 行高,左右边距可以手动控制
    * 容纳性: 行级元素
# 元素转换
    display: block         转为块级元素(会摒弃原有的元素特性)
             inline        转为行级元素
             inline-block  转为内联-块级元素
             table         转为块级表格
             table-cell    转为td单元格
             none          隐藏(不占位)
             
    visibility:hidden      隐藏(占位)
               visibile    显示

# 内外边距
    外边距margin: 元素与元素之间的距离
    单边:
        margin-方向
        
    四边:
        margin: 10px                上下左右均为10px
        margin: 10px 20px           上下10 左右20
        margin: 10px 20px 30px      上10 左右20 下30
        margin: 10px 20px 30px 40px 上10 右20 下30 左40
        
    技巧:
        如何小div在大div中实现水平居中
        小div 方法1:
            margin-left: auto;
            margin-right:auto;
            
        小div 方法2: (简写)
            margin: 0px auto;
            
        垂直居中自己本身的一半:
            transform: translateY(-50%);
     内边距padding: 元素与内容之间的距离
     单边:
        padding-方向:
    
     四边:
        padding: 10px                上下左右均为10px
        padding: 10px 20px           上下10 左右20
        padding: 10px 20px 30px      上10 左右20 下30
        padding: 10px 20px 30px 40px 上10 右20 下30 左40

# 盒子模型

    盒子: 外边距 + 内边距 + 边框 + 内容

    IE:  内容    (IE8-)
         IE8- 浏览器, 一个盒子的物理空间是根据 width/height 而决定
         width/height 包含了padding 和 border

    非IE: 内容 + 内边距 + 边框
          非IE浏览器, 一个盒子的物理空间是根据 width/height + padding + border 而决定

    box-sizing: content-box     (非IE模型)
                border-box      (IE模型)
        
# 浮动
    1.作用
        将竖排 变成 横排
        文字环绕(文字图片)
    
    2.属性
        float: none     不浮动
               left     左浮动
               right    右浮动
               
    3.注意点
        浮动是不保留原来的位置
        
    4.清除浮动
        清除浮动后,能保留浮动元素的位置
        clear: left
               right
               both
    
        方法1: (原理)
            在浮动元素的最后面,添加空标签(不能与浮动是
            同类型标签),并赋予clear属性
            
        方法2: (BFC)
            给浮动元素的父级, 赋予 overflwo:hidden,
            从而清除子集的浮动
            BFC: 能形成完全独立的区域,区域内的内容是不会受影响外部的内容
            
        方法3: 伪对象(推荐)
            给浮动元素的父级,通过伪对象选择器的方式清除子集的浮动
                父级选择器::after{
                    content: ' ';
                    display:block;  |  display:table;
                    clear:both;
                }
# 尺寸
    width:  固定宽度
    height: 固定高度
    min-width:  最小宽度
    min-height: 最小高度
    max-width:  最大宽度
    max-height: 最大高度
    
    当部分盒子宽高由 百分比 进行设置, 视情况而定是否需要最大/最小宽高

# 字体图标
    阿里字体图标
        地址: https://www.iconfont.cn/
    
    1.导入 iconfont.css
    
    2.查看需要用的 字体图标的符号
        demo_index.html

        符号格式
            &代码;

     3. 给当前标签赋予 class="iconfont"

# 定位
    position: absolute 绝对定位
              relative 相对定位
              fixed    固定定位
              
    使用场景:
        当元素发生重叠时,使用定位
        
    绝对定位: absolute
        原来: 基于网页第一页的四个角落
        位置: 不保留原来的位置
    
    相对定位: relative
        原点: 基于原来位置的四个角落
        位置: 保留原来的位置
        
    固定定位: fixed
        原点: 基于可视窗口的四个角落
        位置: 不保留原来的位置
        
    技巧:小div 基于大div的四个角落作为原点
    大div: 相对定位
    小div: 绝对定位
# 定位优先级
    z-index: num数字    num越大,优先级越高
    条件限制: 只有定位元素才能使用
    
# css初始化
    原因: 各大浏览器的部分默认属性值不一致,导致相同的
          页面在不同的浏览器打开效果不一致
    
    目的: 为了统一各大浏览器的默认属性值
    
# 平滑过渡
    transition: 过渡的属性 过渡时间 [速率] [延迟时间]
    
    * 单个属性过渡
        transition: 属性名 过渡时间 [速率] [延迟时间]
        
    * 多个属性过渡
        transition: 属性名1 过渡时间 [速率] [延迟时间],
                    属性名2 过渡时间 [速率] [延迟时间],
                    属性名3 过渡时间 [速率] [延迟时间],...
                    
    * 改变多少属性,就过渡多少属性
        transition: all 过渡时间 [速率] [延迟时间]
        
    * 时间
    *   单位: s / ms          1s = 1000ms

    * 速率
    *   linear 匀速
    *   ease-in 加速
    *   ease-out 减速
    *   ease-in-out 先减速再减速
    *   速度公式 cubic-bezier       (利用F12调整比较方便)

    重点注意: 
        transition 只能用于能够加减的属性

        能加减的属性: px, 颜色, % 等
        不能加减的属性: overflow, display 等

# 变形
    -webkit-   chrome内核, safari内核
    -moz-      firefox内核
    -ms-       IE内核 
    
    transform: [none] | [rotate] | [skew] | [scale] | [translate]

    rotate: 旋转
             单位: deg  角度
             rotate()
             rotateX()
             rotateY()
            

    skew:   扭曲
            单位: deg 角度
            skewX()
            skewY()
            skew(X)
            skew(X,Y)
            
    scale:  中心缩放
            单位: 基数  数字
                  1 是本身
                  >1 放大
                  <1 缩小

    translate: 位移
            单位: px %
            translate(X)
            translate(X,Y)
            translateX()
            translateY()
            注意点: 从当前位置作为起点

# 动画

    动画核心: 规定动画步骤
            * 规定动画: @keyframes
            * 运行动画: animation
                        infinite   无限的循环动画

    规定写法1: 简单步骤
        @keyframes 动画名{
            from{ ... }
            to{ ... }
        }

    规定写法2: 复杂步骤  (掺杂百分比时间点)
        @keyframes 动画名{
            from{ ... }
            25%{ ... }
            50%{ ... }
            75%{ ... }
            to{ ... }
        }

    规定写法3: 复杂步骤
        @keyframes 动画名{
            0%{ ... }
            25%{ ... }
            50%{ ... }
            75%{ ... }
            100%{ ... }
        }

# 多列
    column-count 属性规定元素应该被分隔的列数
    column-gap 属性规定列之间的间隔
    column-rule 属性设置列之间的宽度、样式和颜色规则

    简写:
        columns：宽度px || 列数
        
# 渐变
    语法：
        background: linear-gradient([ 渐变方向 | 角度 ]起止颜色,终止颜色)
        起止颜色:可以设置为方向或角度
                to left：
                设置渐变为从右到左。相当于: 270deg
                to right：
                设置渐变从左到右。相当于: 90deg
                to top：
                设置渐变从下到上。相当于: 0deg
                to bottom：
                设置渐变从上到下。相当于: 180deg。这是默认值，等同于留空不写

# 滤镜
    filter: none 
            blur(px)    高斯模糊。如果没有设定值，则默认是0；这个参数可设置css长度值，但不接受百分比值。
            brightness(%) 亮度  范围0%-100%(0%全黑)值可以超过100%,默认值是1。
            contrast(%)     对比度 范围0%-100%(0%全黑)值可以超过100%,默认值是1
            drop-shadow()   阴影效果
            grayscale(%)    灰度图像  范围0%-100%(0%无变化),值默认是0
            hue-rotate(deg)    色相旋转  
            invert(%)          反转输入图像  范围0%-100%(0%无变化),值默认是0
            opacity()       透明程度    范围0%-100%(0%完全透明)
            saturate()      饱和度  范围0%-100%(0%没效果)值可以超过100%,默认值是1
            sepia()         深褐色     范围0%-100%(0%没效果)   值默认是0
            url()           指定一个具体的滤镜元素
# 网页布局
    PC端常用布局: 
            DIV+CSS
            响应式布局
        
    DIV+CSS: 
        从宏观到微观
        能行则行, 不能行再列

    肉眼识别div嵌套