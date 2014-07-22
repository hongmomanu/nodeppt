title: 前端语法学习之javascript基础
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 前言
----

* 网页的解剖。在我们深入了解JavaScript语言之前, 让我们解剖一下一个网页主要有哪些Web技术. {:&.build} 

* HTML 是内容:
         
    ```bash
             
         HTML是用来定义和描述的内容的标记语言。无论是博客文章，搜索引擎结果，
         或电子商务网站，一个网页的核心内容是用HTML编写的。
         HTML是用来描述内容的通用术语（标题，段落，图片等）  
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* CSS 用来渲染:
         
    ```bash
             
         CSS为HTML文档添加适当风格的附加语言。 
         CSS是所有有关使内容通过定义字体，颜色和其他视觉美感更好看。 
         CSS的强大功能来自于一个事实，即你可以将不同的样式应用到同一块内容，
         构建看跨终端的良好响应的网站时，这是至关重要的。  
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* JavaScript  用来交互:
         
    ```bash
          在浏览器中，JavaScript对HTML内容增添交互性和行为。
          没有JavaScript，网页将是静态的，枯燥的。 
          JavaScript的帮助把一个网页变的有生命。   
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* 看一个简单的例子，看看CSS and JavaScrip是怎么一起工作的:
         
    ```html
        <!doctype html>
        <html lang="zh">
        <head>
            <meta charset="utf-8" />
            <title>Hello World</title>
         
            <!-- CSS for presentation. -->
            <style>
            h1 { font-size: 14px; color: hotpink; }
            button { color: red; }
            </style>
        </head>
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* 续上:
         
    ```html
        <body>
            <h1>Hello World</h1>
            <button>Click Me!</button>
            <!-- JavaScript for interactivity. -->
            <script>
            var button = document.querySelector( "button" );
            button.addEventListener( "click", function( ev ) {
                alert( "Hello" );
            }, false);
            </script>
        </body>
        </html> 
                      
    ```
    
