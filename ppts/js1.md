title: 前端语法学习之jquery介绍
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## Jquery前言
----

* 如果你经常用javascript写前端代码，也许你已经听说过Jquery了。它是目前最为流行的，使用范围最广的，javascript前端库之一。例如微软，Twitter等著名软件公司都在使用它。 {:&.build} 

* Jquery的目标是:
         
    ```bash
             
         “The Write Less, Do More JavaScript Library”   
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]

## Jquery历史
----

* jQuery在2006年1月由美国人John Resig在纽约的barcamp发布，吸引了来自世界各地的众多JavaScript程序员加入，由Dave Methvin率领团队进行开发。 {:&.build} 

* jQuery是免费、开源的，使用MIT许可协议。

* 除此以外，jQuery提供API让开发者编写插件。其模块化的使用方式使开发者可以很轻松的开发出功能强大的静态或动态网页。

* 如今，jQuery已经成为最流行的javascript框架，在世界前10000个访问最多的网站中，有超过55%在使用jQuery.
    
[slide style="background-image:url('/img/bg.jpg	')"]
## 什么是Jquery
----

* jQuery 是一个能够让用javascrpt语法建立页面和应用变的快速和简单的库 。通常一个10-20行用纯的原始的javascript语法写的代码用Jquery代码写也许只需一行。 {:&.build} 

* jQuery自己本身也是用JavaScript写的,最后它以一个单一的js文件形式发布，得以让你的web应用项目引用.然后你可以在你的javascript语句调用Jquery中各种方法函数。

[slide style="background-image:url('/img/bg.jpg	')"]
## 什么是Jquery（续）
----

* The jQuery 文件通常以两种形式发布: {:&.build} 
    
    ```bash
             
         1. The uncompressed .js file 有注释，换行，缩进等，代码较容易阅读，
            但文件比较大，适合开发时引用. 
         
         2. The minified .js file  所有注释换行格式化都被删除，不易阅读，
            但文件较小，适合产品发布时使用。 
                       
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
## 什么是Jquery（续）
----

* 获取Jquery: {:&.build} 
    
    * [Jquery官方网址](https://jquery.org/)
    
    * [未解压缩uncompressed 下载](http://code.jquery.com/jquery-1.11.1.js)
    
    * [压缩minified 下载](http://code.jquery.com/jquery-1.11.1.min.js)


[slide style="background-image:url('/img/bg.jpg	')"]
## 利用网络CDN公共库
----

* 为什么？: {:&.build} 
    
    * 较少本地应用服务器的压力  {:&.build} 
    
    * 最大的优点是许多用户在访问其他站点时，已经从谷歌或微软加载过 jQuery。
      所以结果是，当他们访问您的站点时，会从缓存中加载 jQuery，这样可以减少加载时间。
      同时，大多数 CDN 都可以确保当用户向其请求文件时，会从离用户最近的服务器上返回响应，这样也可以提高加载速度。
    
   
[slide style="background-image:url('/img/bg.jpg	')"]
## 利用网络CDN公共库（续）
----

* 下面就介绍几个相对来说比较稳定的CDN公共库: {:&.build} 
    
    * [Google CDN](http://ajax.googleapis.com/ajax/libs/jquery/1.7/jquery.min.js)  {:&.build} 
        ```html
            <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7/jquery.min.js"></script>
        
        ```
    * [Microsoft CDN](http://ajax.microsoft.com/ajax/jquery/jquery-1.7.min.js)  
        ```html
            <script type="text/javascript" src="http://ajax.microsoft.com/ajax/jquery/jquery-1.7.min.js"></script>
      
        ```
    
[slide style="background-image:url('/img/bg.jpg	')"]
## 利用网络CDN公共库（续）
----

* CDN公共库(续): {:&.build} 
    
    * [百度 CDN](http://libs.baidu.com/jquery/1.7.0/jquery.min.js) 
        ```html
            <script type="text/javascript" src="http://libs.baidu.com/jquery/1.7.0/jquery.min.js"></script>
          
        ```
    * [新浪 CDN](http://lib.sinaapp.com/js/jquery/1.7/jquery.min.js)
        ```html
              <script type="text/javascript" src="http://lib.sinaapp.com/js/jquery/1.7/jquery.min.js"></script>
        ```    
   
[slide style="background-image:url('/img/bg.jpg	')"]
## 利用网络CDN公共库（续）
----

* 以防万一，当无法从CDN服务器上获取jQuery时，则使用本地jQuery: {:&.build} 
    
    ```html
        <script type="text/javascript">window.jQuery||document.write('<script src="jquery.js"><\/script>');</script>
      
    ```
    




[slide style="background-image:url('/img/bg.jpg	')"]
## What can you do with jQuery?
----

* jQuery可以很容易地编写功能强大的JavaScript应用程序和创建引人注目的动画效果。诸如此类，jQuery可以做到下面事情: {:&.build} 
    
    * 对元素增加动态的效果.jQuery的可以让你轻松地添加效果，如淡入/淡出，内/外滑动，并展开/收缩。
    
    * Making  Ajax 请求. These use JavaScript to request additional data from the Web server without having to reload the page.
    
    * 操作 DOM. 您可以轻松地只用几行代码来添加，删除和修改网页的内容。


[slide style="background-image:url('/img/bg.jpg	')"]
## What can you do with jQuery?（续）
----
    
* 创建图像幻灯片。你可以使用jQuery特效打造漂亮的动画幻灯片。   {:&.build} 

* 制作下拉菜单。 jQuery的可以很容易地创建带有动画的多层次的下拉菜单。

* 创建拖动和拖放界面。使用jQuery来构建与可以简单地通过拖放重新定位或重新排序元素的网页。

* 添加强大的表单。使用jQuery，您可以轻松添加复杂的客户端表单验证，建立通过ajax从服务器端获取数据的文本等。

[slide style="background-image:url('/img/bg.jpg	')"]
## 最让人省心的特点
----
    
* 另一个jQuery的优势在于，它可以很容易地编写JavaScript在许多不同的浏览器工作。  {:&.build} 

* 流行的浏览器，如IE浏览器之间的不兼容性，以及Firefox，Safari，chrome之间的不兼容性。
   
* 因此你经常需要编写不同的JavaScript代码块来兼容他们，增加开发的复杂度。
   
* 但是使用jQuery，你只需要调用相应的jQuery函数，让jQuery来自动生成不同的运行在不同的浏览器下的代码！  

[slide style="background-image:url('/img/bg.jpg	')"]
## 关于Jquery的版本
----
    
* Jquery1.x 支持ie6以上浏览器，对于旧的浏览器兼容更好。  {:&.build} 

* Jquery2.x 不支持ie8以下的浏览器，所以更加轻量级，对新的浏览器特性如html5特性支持更好。  

[slide style="background-image:url('/img/bg.jpg	')"]
## 用一个例子说明Jquery是如何工作的
----
    
* 首先，引用Jquery，我们新建一个HTML 文件，如下:  {:&.build} 
    ```html
       <!doctype html>
       <html>
       <head>
           <meta charset="utf-8" />
           <title>Demo</title>
       </head>
       <body>
           <a href="http://jquery.com/">Hello jQuery</a>
           <script src="jquery.js"></script>
           <script>
           // 写你的代码.
           </script>
       </body>
       </html>
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Launching Code on Document Ready
----
    
* 为了保证javascript的代码在浏览器完成加载document之后运行,
    很多javascript开发者将他们的代码写在 onload function 里面，如下:  {:&.build} 
    ```javascript
    
       window.onload = function() {
           alert( "welcome" );
       }
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Launching Code on Document Ready （续）
----
    
* 不幸的是，上面的代码，直到所有图像下载完毕，代码才运行。为了解决此问题，尽快的运行代码，jQuery用ready事件的声明：:  {:&.build} 
    ```javascript
    
       $(document).ready(function() {
           // Your code here.
       });
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  增加一个单击事件
----
    
* 例如,在ready event 里面, 你可以添加一个添加一个单击事件:  {:&.build} 
    ```javascript
    
       $( document ).ready(function() {
        
           $( "a" ).click(function( event ) {
        
               alert( "Thanks for visiting!" );
        
           });
        
       });
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  阻止跳转
----
    
* 对于单击或者其它大部分事件, 你可以通过调用event.preventDefault()阻止默认的行为，如下:  {:&.build} 
    ```javascript
    
       $( document ).ready(function() {
        
           $( "a" ).click(function( event ) {
            
                   alert( "正如你所见,我不将再跳往jquery首页");
            
                   event.preventDefault();
            
           });
        
       });
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Adding and Removing an HTML Class
----
    
* 首先, 增加一些样式到document里的<head>标签下 , 如下:  {:&.build} 
    ```html
    
       <style>
       a.test {
           font-weight: bold;
           color:red;
       }
       </style>
    
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Adding and Removing an HTML Class （续）
----
    
* 执行 .addClass() 以增加class:, 如下:  {:&.build} 
    ```javascript
       
       $( "a" ).addClass( "test" );
       
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Adding and Removing an HTML Class （续）
----
    
* 执行 .removeClass() 以删除样式:, 如下:  {:&.build} 
    ```javascript
       
       $( "a" ).removeClass( "test" );
       
    ```


[slide style="background-image:url('/img/bg.jpg	')"]
##  特别效果 
----
    
* jQuery的也提供了一些方便的效果。例如，你可以添加一个渐渐消失的效果，只需添加如下代码：  {:&.build} 
    ```javascript
       
       $( "a" ).click(function( event ) {
        
           event.preventDefault();
        
           $( this ).hide( "slow" );
        
       });
       
    ```


[slide style="background-image:url('/img/bg.jpg	')"]
##  Callbacks 
----
    
* Callback without Arguments：  {:&.build} 
    ```javascript
       
      $.get( "hello.html", function(){
            alert(1);
      });
       
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  Callbacks(续) 
----
    
* Callback with Arguments：  {:&.build} 
    ```javascript
       
      $.get( "hello.html", function(data){
            alert(data);
      });
       
    ```

[slide style="background-image:url('/img/bg.jpg	')"]
##  课后作业 
----
    
* 使用jquery做出图片渐入渐出效果

* 演示一下

* 邮箱地址 hongmomanu@163.com


