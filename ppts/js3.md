title: 前端语法学习之jquery语法基础
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## $ 和 $()
----

* $ 一般是一些自带的实用函数方法，如: {:&.build} 
    ```javascript
             
         $.trim("123   ");  
                      
    ```

* $()一般是用来选择元素，并对选择的元素进行操作,如:
         
    ```javascript
             
         $( "h1" ).remove();  
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]    
## $( document ).ready()写法
----

* 标准用法:  {:&.build} 
         
    ```javascript
             
         $( document ).ready(function() {
             console.log( "ready!" );
         });
                      
    ```
* 简写用法:  
         
    ```javascript
             
         $(function() {
             console.log( "ready!" );
         });
                      
    ```
、    
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## $( document ).ready()写法（续）
----

* 分开命名法:  {:&.build} 
         
    ```javascript
             
         function readyFn( jQuery ) {
             console.log( "ready!" );
         }
          
         $( document ).ready( readyFn );
                      
    ```
    
    
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 避免与其他库的冲突
----

* 当项目中存在其它库，如prototype.js, MooTools, or YUI时，可能会发生冲突，这时候你需要启用No-Conflict 模式:   {:&.build} 
         
    ```html
          <!-- Putting jQuery into no-conflict mode. -->
          <script src="prototype.js"></script>
          <script src="jquery.js"></script>
          <script>
          var $j = jQuery.noConflict();
          // $j is now an alias to the jQuery function; creating the new alias is optional.
          $j(document).ready(function() {
              $j( "p" ).hide();
              var mainDiv = $( "main" );
              alert(mainDiv);
          });
          </script>  
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## 避免与其他库的冲突(续)
----

* 如果你不想定义另一个替代全jQuery函数的别名，你也可以这样写:   {:&.build} 
         
    ```html
          <!-- Putting jQuery into no-conflict mode. -->
          <script src="prototype.js"></script>
          <script src="jquery.js"></script>
          <script>
          jQuery.noConflict();
           
          jQuery( document ).ready(function( $ ) {
              
              $( "p" ).hide();
          });
          
          </script>  
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"]     
## 避免与其他库的冲突(续)
----

* 包括其他的jQuery库之前:   {:&.build} 
         
    ```html
          <!-- Putting jQuery into no-conflict mode. -->
          <script src="jquery.js"></script>
          <script src="prototype.js"></script>
          <script>
          jQuery.noConflict();
           
          jQuery( document ).ready(function( $ ) {
              
              $( "p" ).hide();
          });
          
          </script>  
              
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## The .attr() 方法
----

* ATTR（）方法同时充当一个getter和setter。ATTR（）可以接受一个键和一个值，或包含一个或多个键/值对的对象。.attr() as a setter:   {:&.build} 
         
    ```javascript
        $( "a" ).attr( "href", "http://www.baidu.com" );
        $( "a" ).attr({
            title: "九宵环佩",
            href: "http://www.baidu.com"
        });              
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## The .attr() 续
----

* .attr() as a  getter:   {:&.build} 
         
    ```javascript
        console.log($( "a" ).attr( "href"));
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素
----

* jQuery的最基本概念是“选择一些元素，然后对他们做一些事。”
  jQuery的支持大部分CSS3选择器. {:&.build} 

* Selecting Elements by ID         
    ```javascript
    
        console.log($( "#myId" ).html());  
                     
    ```
* Selecting Elements by Class Name         
    ```javascript
    
         console.log($( ".myClass" ).html());  
                   
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

* Selecting Elements by Attribute: {:&.build} 
         
    ```javascript
        
        $( "div[name='div_name']");
                      
    ```
* Selecting Elements by Compound CSS Selector: {:&.build} 
         
    ```javascript
        
       $( "#myId ul.people li" ); 
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

* 其它一些选择例子。: {:&.build} 
         
    ```javascript
        
        $( "a.external:first" );
        $( "a:odd" );
         
        // Select all input-like elements in a form (more on this below).
        $( "#myForm :input" );
        $( "div:visible" );
         
        // All except the first three divs.
        $( "div:gt(0)" );
         
        // All currently animated divs.
        $( "div:animated" );
                      
    ```
    
