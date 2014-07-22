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

* CSS 用来渲染:  {:&.build} 
         
    ```bash
             
         CSS为HTML文档添加适当风格的附加语言。 
         CSS是所有有关使内容通过定义字体，颜色和其他视觉美感更好看。 
         CSS的强大功能来自于一个事实，即你可以将不同的样式应用到同一块内容，
         构建看跨终端的良好响应的网站时，这是至关重要的。  
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* JavaScript  用来交互:   {:&.build} 
         
    ```bash
          在浏览器中，JavaScript对HTML内容增添交互性和行为。
          没有JavaScript，网页将是静态的，枯燥的。 
          JavaScript的帮助把一个网页变的有生命。   
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 前言（续）
----

* 看一个简单的例子，看看CSS and JavaScrip是怎么一起工作的:   {:&.build} 
         
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
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 运行代码
----

* 从外部引入.最优先和建议的选项是在外部文件（扩展名为。js扩展名）编写代码，
  然后可以使用HTML script标签和指向src属性文件的位置被包含在我们的网页。
  如果你想重新使用它在其他页面，在一个单独的文件会减少代码重复。
  它也将允许在远程客户端的计算机上的浏览器缓存文件，减少页面加载时间.: {:&.build} 
         
    ```html
        
        <script src="/path/to/example.js"></script>
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 运行代码(续)
----

* 内嵌运行。第二个选项是直接内联代码在网页上。
  这也需要使用HTML script 标记，但不是指向src属性到一个文件中，代码被放置在标签之间。
  虽然也有这样使用的运行代码的情况，但大部分的时间，最好是保持我们的代码在上面讲的外部文件中来引用。: {:&.build} 
         
    ```html
        
        <script>
        alert( "Hello World!" );
        </script>
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 运行代码(续)
----

* 在属性中。最后一个选项是使用HTML元素的事件处理属性。这种写法维护困难，可扩展性差，无法重复利用，解藕性差，是强烈反对的：。: {:&.build} 
         
    ```html
        
        <a href="javascript:alert( 'Hello World' );">Click Me!</a>
        <button onClick="alert( 'Good Bye World' );">Click Me Too!</button>
                      
    ```
    
