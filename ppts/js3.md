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

* 判断是否找到元素，如果你做了一个选择,你想知道是否找到了元素.一个常见的错误是: {:&.build} 
         
    ```javascript
        
        // Doesn't work!
        if ( $( "div.foo" ) ) {
        
            console.log("存在");
            
        }else{
        
            console.log("不存在");
        }  
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

* 正确的用法是: {:&.build} 
         
    ```javascript
        
       if (  $( "div.foo" ).length  ) {
       
           console.log("存在");
           
       }else{
       
           console.log("不存在");
           
       }     
                      
    ```    

[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

* 重复利用.jQuery的不缓存你的元素。如果你做了一次选择，你可能需要再次需要选择，你应该保存选择的变量，而不是重复地做选择。: {:&.build} 
         
    ```javascript
        
       var divs = $( "div" );  
                      
    ```    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

* 常用的form元素选择。: {:&.build} 
         
    ```javascript
        
       $( "form :button" );
       $( "form :checkbox" );
       $( "form :checked" );
       $( "form :disabled" );
       $( "form :enabled" );
                      
    ```    
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 选择元素(续)
----

*  常用的form元素选择（续）： {:&.build} 
         
    ```javascript
        
       $( "form :file" );
       $( "form :image" ); 
       $( "form :input" );
       $( "form :password" );
       $( "form :radio" );
                      
    ```    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 使用选择
----

* Getters & Setters。当一个方法被用来设置一个值，它被称为一个setter。
   当一个方法被用来获取（或读取）的值，它被称为一个getter。setter影响选择的所有元素。getter仅获取在选择的第一要素所要求的值。 : {:&.build} 
         
    ```javascript
        
       $( "h1" ).html( "hello world" );
       
       $( "h1" ).html();
                      
    ```    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 使用选择（续）
----

* Chaining。如果你调用一个选择的方法，而且该方法返回一个jQuery对象，你可以继续在对象上调用jQuery方法。
  这种做法被称为“链式操作”：: {:&.build} 
         
    ```javascript
        
       $( "body" ).find( "h1" ).eq( 0 ).html( "new text for the first h1!" );
                      
    ```
* 为了增加可读性.你也可以这样写:
    
    ```javascript
            
        $( "body" )
            .find( "h1" )
            .eq( 0 )
            .html( "new text for the first h1!" );
                          
    ```    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 使用选择（续）
----

* 对于“Chaining”，jQuery的还提供了end（）方法来返回到原来的选择：: {:&.build} 
         
    ```javascript
        
       $( "body" )
           .find( "h1" )
           .eq( 1 )
               .html( "new text for the third h1!" )
               .end()
           .eq( 0 )
               .html( "new text for the first h1!" );
                      
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Getting and Setting Information About Elements，介绍如下： {:&.build} 
         
    ```javascript
        
       .html() – Get or set the HTML contents.
       .text() – Get or set the text contents; HTML will be stripped.
       .attr() – Get or set the value of the provided attribute.
       .width() – Get or set the width in pixels of the first element in the selection as an integer.
       .height() – Get or set the height in pixels of the first element in the selection as an integer.
       .position() – Get an object with position information for the first element in the selection, relative to its first positioned ancestor. This is a getter only.
       .val() – Get or set the value of form elements. $( "form :input" ).val();
                      
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Moving Elements，方法有.insertAfter(), .insertBefore(), .appendTo(), and .prependTo() ： {:&.build} 
         
    ```javascript
       
       var li = $( "ul.people li:first" ).appendTo( "ul.people" );
        
       // Another approach to the same problem:
       $( "ul.people" ).append( $( "ul.people li:first" ));
                      
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Cloning Elements，方法为.clone() ： {:&.build} 
         
    ```javascript
       
       // Copy the first list item to the end of the list:
       $( "ul.people li:first" ).clone().appendTo( "ul.people" );
                      
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Removing Elements，方法为.remove() ： {:&.build} 
         
    ```javascript
       
       // Copy the first list item to the end of the list:
       $( "ul.people li:first" ).remove() ;
       //只想清空内容
        $( "ul.people li:first" ).empty() ;               
    ```
[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Creating New Elements，方法为$("...")  ： {:&.build} 
         
    ```javascript
       
       // Creating new elements from an HTML string.
       $( "<p>This is a new paragraph</p>" );
       $( "<li class=\"new\">new list item</li>" );
                  
      // Creating a new element with an attribute object.
      $( "<a/>", {
          html: "This is a <strong>new</strong> link",
          "class": "new",
          href: "foo.html"
      });            
    ```

[slide style="background-image:url('/img/bg.jpg	')"]    
## 操纵要素
----

* Creating New Elements(续)  ： {:&.build} 
         
    ```javascript
       
       var myNewElement = $( "<li>New element</li>" );
        
       myNewElement.appendTo( "ul.people" );
        
       myNewElement.insertAfter( "ul.people li:first" ); 
        
       $( "ul.people li:first" ).after( myNewElement.clone() ); 
              
    ```
