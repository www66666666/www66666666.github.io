<font style="font-size:1.3em;font-weight:bold;"> 目录 </font> 
[toc]

# jQuery 简介
    1. jQuery 简介
        jQuery是一个JavaScript函数库, 也是Js中轻量级框架之一
        jQuery的初始: 写得少, 做得多
        优势: 
         * 开源
         * 选择器便捷
         * DOM操作方便
         * 兼容性
         * 简化Ajax操作
         * 支持插件扩展

    2. jQuery版本
        至今2019年, 最新版 jQuery3.4.1

        官方地址: https://jquery.com/
        版本地址: https://code.jquery.com/

        jQuery 一般分为: 
            压缩版:   jQuery-3.4.1.min.js 
                      体积小, 适用于实际项目

            未压缩版: jQuery-3.4.1.js
                      体积大, 适用于阅读源码

    3. jQuery插件网
        * http://www.jq22.com
        * http://www.htmleaf.com/jQuery/
        * https://www.php.cn/xiazai/js

    4. jQuery 使用
        $(选择器).方法()
    
    5. 全局加载
        默认情况: js在前, html在后, js无法使用后面的html
        结局方案: 
            原生Js: onload 全局加载: 当整个网页加载好了(包含视频, 图片), 再执行onload里面的js
                                     没有简写
                                     只能执行一次, 如果有第二个onload, 会覆盖前一个

            jQuery: ready 全局加载: 只需要DOM结构加载完成后, 就能执行ready里面的js
                                     有简写
                                     可以执行多次, 第N个都不会覆盖前一个ready

            标准ready
                $('document').ready(function(){

                });
        

            简化ready
                $(function(){

                })

    6. 命名
        $ 是jQuery的别名, 所以变量取名最好避免使用$
        
        
    <div id="box"></div>
    <script>
        // var $ = 100;
        // console.log($);

        // $('#box').hide()
        // $('#box').show()
        // console.log(  $('#box') );




        // 原生全局加载
        // window.onload = function(){
        //     $('#box').hide()
        // }


        // jQuery全局加载
        // $('document').ready(function(){
        //     $('#box').hide()
        // });


        // jQuery 简化全局加载的写法
        // $(function(){
        //     $('#box').hide()
        // });
        
    </script>    
        
# 选择器

    <ol id="hero">
        <li>李白</li>
        <li>阿珂</li>
        <li>
            师徒四人
            <ul class="list A">
                <li>唐僧</li>
                <li class='pig'>八戒</li>
                <li>悟空</li>
                <li>沙僧</li>
            </ul>
        </li>
        <li>
            五虎上将
            <ul class="list B">
                <li>关羽</li>
                <li>张飞</li>
                <li>赵云</li>
                <li>马超</li>
                <li>黄忠</li>
            </ul>
        </li>
        <li>韩信</li>
    </ol>

    <script>
        
        $(function(){

            // console.log(  $('#hero')  );
            // console.log(  document.getElementById('hero')  );


            // id
            // $('#hero').css('color','red');


            // class
            // $('.list').css('color','red')


            // 标签名
            // $('li').css('color','red')


            // 同时给不同的选择器赋予css
            // $('.A, .B').css('color','red');



            // s1 s2
            // $('.A li').css('color','red');

            // s1 > s2
            // $('.A > li').css('color','red');

            // s1 + s2
            // $('.pig + li').css('color', 'green');

            // s1 ~ s2
            // $('.pig ~ li').css('color', 'green');



            // :first
            // $('.list:first').css('color','blue');
            // $('.list li:first').css('color','pink')

            // :eq(index)           index:索引
            // $('.list:eq(0)').css('color','red');
            // $('.list:eq(1)').css('color','red');
            // $('.list:eq(1)').css({
            //                         'color':'red',
            //                         'background':'pink',
            //                         'fontSize':'20px',
            //                     });

        });
    
    </script>
    
# 