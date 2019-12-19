<font style="font-size:1.3em;font-weight:bold;"> 目录 </font> 
[toc]

# HTML网页文件格式

``` 
格式:  *.html
标准命名: 允许有数字,字母和下划线
		不允许特殊字符 / | \ : < > " * ? (系统不支持)

```

## 全局架构标签
    
     html: 网页声明, 告诉浏览器, 这里面都是html代码 
     head: 头部声明, 可声明网页标题, 编码, 导入css, js 等文件
     body: 主体声明, 主要展示文字, 图片, 视频, 音频等内容

     一个标准的网页, 全局架构标签是必不可少的 ( H5是可以省略全局架构标签, 但不推荐 )

## 文档声明

    目前 HTML 已发展到第5版, 称之为"HTML5", 俗称"H5", 现已成为市场主流
    H5声明: <!DOCTYPE html> 

    若将来看到如下声明: 
        <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
    请注意, 这是H4的声明写法, 
    此写法已经慢慢淡出市场, 大家了解即可
    
## ​注释

    作用: 为代码做一些描述, 方便自己or其他程序员阅读
    格式: <!--  注释内容  - ->
    格式注意点: 注释不要嵌套使用
    内容注意点: 注释尽可能精简直白, 去除不必要的废话
    
    代码规范: https://www.runoob.com/html/html5-syntax.html

# 标签

    是网页的最主要的组成部分

## 分类

    ```
    单标签: <开始标签名>
    双标签:<开始标签名> 正文内容 </结束标签名>
    
    正文内容可以是:数字, 字母, 汉字和标点,甚至是标签(不是所有的标签都可以互相嵌套)
    ```

## 属性

    是给元素(标签)额外添加一些功能
    大部分标签都会有一些专属属性, 小部分没有专属属性
    
    格式: <开始标签  属性名1="属性值1" 属性名2="属性值2" ... >
    格式注意点: 
        * 属性由 属性名和属性值 组成
        * 属性值 最好用 引号 包起来 (单引号 or 双引号都可以, 没区别)
        * 属性只能写在 开始标签中
        * 属性与标签之间 至少保留1个空格
        * 属性与属性之间 至少保留1个空格 
    
    每个标签都会有哪些属性呢?
            参考地址: https://www.runoob.com/tags/html-reference.html

            该地址中, 有HTML所有的标签, 点击标签名, 即可查看到该标签能使用的属性

            友情提醒: 有的属性确实存在, 但是有的已经被弃用, 此类属性建议少用, 最好不用, 防止部分浏览器显示不出效果


    换行: 	<br>
    水平线:   <hr>
    
    width   宽度
    		%百分比
    		px 像素	在html属性值中,可省略px,默认单位就是px
    
    align 	水平对齐方式
    		left	左
    		right	右
    		center	居中


# 文本标签

修饰文字的相关标签

## 标题标签

    h1, h2, h3, h4, h5, h6
    h1最大, h6最小
    
    注意: 在一个HTML页面, 只能使用1次h1标签
         h1具有提高搜索引擎排名的功能 (优化SEO)
         
    	如果一个HTML页面中, 出现多次h1, 则被搜索引擎认为恶意提高排名,
        此种情况将会直接拉入黑名单


## 段落标签

        文章段落
        特点: 上下文的间距比较大, 独占一行
        格式: <p> </p>

    换行/拆行
        <br> 标签, 主动换行

## 文本格式化
    样式化标签
        |        |      |
        | :----: | ---- |
        |  加粗  | b    |
        |  倾斜  | i    |
        | 下划线 | u    |
        | 删除线 | del  |
    
    语义化标签
        强调: strong
        强调: em

    样式化标签: 本身只具备特殊效果, 表面看上去有所区别
    语义化标签: 不仅具有样式意义, 还有特殊意义

## 原样输出标签

< pre >

## 上下标签

sup 		上标

sub 		下标

# 列表标签

**常用场景:**

​	当发生一排排 or 一列列长得差不多, 只是内容不一样的, 都可以使用 列表标签

## 无序标签

```
<ul>
	<li></li>
	...
	<li></li>
</ul>
```

## 有序标签

```
<ol>
	<li></li>
	...
	<li></li>
</ol>
```

## 定义标签

```
<dl>
	<dt></dt>
	<dd></dd>
	...
	<dd></dd>
</dl>
```

# 浏览器的特性

```
在大多数浏览器中, 
	代码中 输入连续多个空格 or 回车 
	浏览器 要么不解析, 要么只解析成一个空格

所以, 对于程序员而言, 可以利用该特性, 对代码进行排版,
排成程序员看的舒服的排版

	父子级之间需要用 Tab 退格
    向后退: Tab
    向前伸: Shift + Tab
```

# 实体符号

```
实体符号:  将特殊字符 变成 普通字符, 不再具有特殊意义
           长得比较奇葩的字符

空格:    &nbsp;        
小于号:  &lt;
大于号:  &gt;
版权:    &copy;       copyright
人民币:  &yen;

```

# 超链接

```
标签名: a
属性:	
	href = 网页地址 	(若地址为空,则默认链接到本页面)
	target = 窗口
		常见窗口:_self		在本窗口打开链接,默认
				_blank	   在新的窗口打开链接
				_top 	   在顶级窗口打开链接
				自定义 	 在自定义窗口打开链接
	title = 文字提示
	
	<!-- 在新标签页打开链接 -->
    <a href="http://www.taobao.com"  target="_blank">淘宝</a>
```

# URL

```
url 俗称:网址	术语:统一资源定位器
网址组成:
	基本: 协议 + 域名
	完整: 协议 + 域名 + 端口 + 路径 + 参数 + 锚点

完整:http://www.baidu.com:80/xxx/jpg/xxx.html?name=xxx&age=18#xxx

协议:http
    访问网页 http
    文件传输 ftp

域名:www.baidu.com
	所有的域名本质其实是IP地址
	所有的电脑想要上网,都需要IP才能真正的上网
	域名的主要作用: 方便人记忆上网

端口: :80
	  80端口后面就是http网页浏览
      21端口后面就是ftp文件传输
      23端口后面就是telnet远程控制
      其余端口后面都是不同的功能
      
路径: xxx/jpg/xxx.html
	 任何url最终都会指向一个文件
	 特殊的文件名: index
	 特殊之处: 再打开一个文件夹时,若里面含有index文件,
	 		  那么会自动执行该文件
	 	
参数: ?name=xxx&age=18
	 url一旦出现第一个?,意味着后面跟的都是参数
	 每一对参数格式: 参数名=参数值
	 参数值不要加引号
	 每一对参数之间用 & 隔开
	 参数中不要随意输入空格等特殊符号
	 
	 参数作用:在访问网页,需要带额外的东西,那么就称之为参数
	 
锚点: #xxx
	 准备锚点名
	 	html4: <a href="" name="锚点名">
	 	html5: <a href="" id="锚点名">
	 	
	 跳转至锚点
	 	<a href="网页地址#锚点名"></a>
```

# 图片
            格式: <img src="" >
            属性: 
                src     图片来源地址
                alt     当图片加载延迟or失败时, 显示alt内容
                title   当鼠标悬停在图片上时, 显示title内容
                width   设置图片的宽度
                height  设置图片的高度

        注意: 
            * img 不要同时设置width 和 height, 会影响图片原有的宽高比例
# 路径	
    文件路径:
            适用于所有的文件, 涵盖范围: HTML, CSS, JS, PHP, Java, Python ...

    路径分类: 
        相对路径:  
            .       当前目录, 默认, 可省略
            ..      上一级目录

            /       根目录, 写在最前面的/ 才是根目录
                    根目录在后期不同的开发环境下, 根目录地址也会随之发生变化

                    双击打开html文件, 如果在 c盘或d盘打开文件 ( 盘符取决于你的文件在哪个盘里面)
    
        绝对路径: 
            网址形式: 
            盘符形式:

            绝对路径的优势: 不用考虑执行文件本身的位置

# 音频: 

    格式: <audio></audio>
    属性: 
        controls    控制器
        loop         循环播放
        autoplay     自动播放
        src          音频来源地址


    媒介标签:
        格式: <source>
        属性: 
            src          音频来源地址

# 视频

    格式: <video></video>
    属性: src       视频来源地址
          controls  控制器
          loop      循环播放
          autoplay  自动播放

# 表格

    设计表格:  先行再列

    表格
        table   表格声明
        caption 表格标题
        tr       表行
        th       表头单元格      自带水平垂直居中 且 加粗
        td       普通单元格      自带水平左对齐, 垂直居中对齐

    表格属性
        border = "px"  边框
        width
        height
        align = left | center | right   水平对齐方式
        valign = top | middle | bottom  垂直对齐方式

        cellspacing     外边距: 单元格与单元格之间的距离
        cellpadding     内边距: 单元格与内容之间的距离

        rowspan     行合并
        colspan     列合并

        bgcolor      背景颜色
        

    注意: 
        行列合并时, 选择一行or一列的第一个进行合并
# 表单

## 表单声明

​  表单主要目的: 与用户进行交互

    表单标签
        form    表单声明
        input
        select
        button
        textarea

    form属性
        action  将表单提交给 xx服务器
                 action为空, 默认提交给本页面

        method  以什么方式提交给 xx服务器
                 method 为空, 默认为get
            get  明文传输   默认
                  安全性低
                  速度快
                  传输大小: 在HTTP协议没有任何限制, 实际情况是受浏览器的限制( 大部分小于等于 2KB )
                  适用场景: 查询

            post 密文传输
                  安全性高
                  速度慢
                  适用场景: 增删改  (能改变服务器, 隐私性较高)
                  传输大小: 在HTTP协议没有任何限制, 实际情况受限于服务器性能

        enctype = multipart/form-data   专门用于上传文件
    
        上传文件有3个必要条件: 
        * form的enctype=multipart/form-data
        * form的method=post
        * file的name必须要有值
## 表单标签

     1. input 标签
         属性: 
            name    所有的表单都必须要有name属性, 没有name, 就没法提交给服务器
            value   表单数据值
                     可以手动输入的表单: value可写可不写
                     不可以手动输入的表单: value必须写
            type    
                    text        文本域, 可输入数字, 字母, 汉字, 标点等, 默认
                    password    密码域
                    radio       单选
                    checkbox    复选
                    file        文件
                    hidden      隐藏
                    submit      提交

            HTML5新增的type属性       
                    email       邮箱
                    url         网址
                    number      数字
                    date        日期

        注意: 
            * 所有表单都需要name 属性
            * value 默认表单值
                可以手动输入的表单: value可写可不写
                不可以手动输入的表单: value必须写
            * radio单选 和 checkbox多选, 同类型的name必须一致
            * checkbox的name值需要补上[] , 才能形成真正的多选

            * 文件多选
                - file表单必须添加 multiple
                - file表单name值需要补上[] , 才能形成真正的多选
       
    2.select 下拉框标签
        父级标签: select
        子级标签: option   optgroup 

        注意: 
            select 赋予name
            option 赋予value
                
    3.textarea 多文本域标签
        属性:
            name
            rows 行数
            cols 列数
            
            注意: 
            大多数的表单默认值都是通过 value 属性

            多文本域的默认值是: 正文文本
    
    4.button 标签
        submit 只是单纯的提交给服务器
        button 既具有提交给服务器的功能, 又有自定义功能(配合js使用)
    
    5.关联标签 label
            将表单与文本进行关联, 选择文本如同选择表单
            
## 表单常用属性

        maxlength = 最大长度
        minlength = 最小长度
        placeholder = 背景字
        autocomplete = On/Off   输入字段是否应该启用自动完成功能
     以下属性是布尔值可直接写   
        autofocus   自动获取光标
        require     必填（或必选）字段
        multiple    多个值文件上传
        checked     预先选定复选框或单选按钮。
        selected    预先选择一个选项
        readonly    只能看,不能改
        disabled    禁用一个 input 元素

# frame框架

    在HTML5已经淘汰, 不过目前市场仍有部分网站在使用frame, 这里简单的介绍

    重点: frameset 和 body 两者不能共存, 两者只能存其一

    框架设置标签: frameset
    框架标签: frame
    框架就是窗口

    frameset属性
        rows 行分
        cols 列分
        noresize   禁止窗口的拖动
        frameborder  窗口边框, 值: 0 或 非0

        注意: rows 和 cols的单位: px 或 % 或 *
              * 星号代表剩余的空间
    
    frame属性
        src  窗口内容的来源

    窗口划分原则: 先行再列
    
#  内联框架: iframe

    (重点) 可以与body共存, 在body占一个小空间, 独立展示别的网页内容(广告)

      标签: iframe
      属性: 
           name = 窗口名
           src = 窗口内容来源地址
           frameborder = 0 或 非0  窗口边框
           width = 窗口的宽度
           height = 窗口的高度
           scrolling = yes 或 no 或 auto   滚动条的显示状态
           
# head头标签


    ​<! -- 1. 编码设置 -->
    <meta charset="UTF-8">
    
    <!-- 2. 网页标题 -->
    <title>head头标签</title>
    
    <!-- 3. 关键字 -->
    <meta name="keywords"  content="烤鸡, 烤鸭, 烤猪, ...">
    
    <!-- 4. 描述 -->
    <meta name="description" content="这里有大家最喜欢的烤鸡, 烤鸭, 烤猪, ...">
    
    <!-- 5. 重定向 -->
    <!-- <meta http-equiv="refresh" content="秒数;url=地址"> -->
    <!-- <meta http-equiv="refresh" content="5;url=https://www.baidu.com"> -->
    
    <!-- 6. 导入css -->
    <!-- <link rel="stylesheet" href="css文件地址"> -->
    <link rel="stylesheet" href="./demo.css">
    
    <!-- 7. 导入icon -->
    <link rel="icon" href="./favicon.ico">
    
    <!-- 8. 导入js -->
    <!-- <script src="js文件地址"></script> -->
    <script src="./demo.js"></script>


        目前已学能提高 搜索引擎排名的标签:
            h1标签
            title标签
            关键字meta
            描述meta
    