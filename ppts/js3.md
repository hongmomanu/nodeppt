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
* 简写用法:  {:&.build} 
         
    ```javascript
             
         $(function() {
             console.log( "ready!" );
         });
                      
    ```
* 分开命名法:  {:&.build} 
         
    ```javascript
             
         function readyFn( jQuery ) {
             console.log( "ready!" );
         }
          
         $( document ).ready( readyFn );
                      
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
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 运行代码(续)
----

* 运行位置。在节点加载之前。: {:&.build} 
         
    ```html
        
        <!doctype html>
        <html>
        <head>
            <script>
            // Attempting to access an element too early will have unexpected results.
            var title = document.getElementById( "hello-world" );
            console.log( title );
            </script>
        </head>
        <body>
         
        <h1 id="hello-world">Hello World</h1>
         
        </body>
        </html>
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]        
## 运行代码(续)
----

* 运行位置。在节点加载之后。: {:&.build} 
         
    ```html
        
        <!doctype html>
        <html>
        <body>
        <h1 id="hello-world">Hello World</h1>
          <script>
            var title = document.getElementById( "hello-world" );
            console.log( title );
          </script>
        </body>
        </html>
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 语法基础知识
----

* 空白。在JavaScript中空白也是被忽略的，通常添加空白是为了可读性。: {:&.build} 
         
    ```javascript
        
        //添加空白，较好阅读!
        var foo = function() {
            for ( var i = 0; i < 10; i++ ) {
                alert( i );
            }
        };
        foo();
        // 较少空白，不好阅读!
        var foo=function() {for(var i=0;i<10;i++){alert(i);}};foo();
                      
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 语法基础知识（续）
----

* 标识符。标识符是用来给变量和函数的唯一名称，使他们随后可以通过该名称被引用。标识符的名称必须遵循一些规则：。: {:&.build} 
* 不能是保留字。
* 只能由字母，数字，美元符号和下划线。 
* 第一个字符不能是数字.
    

[slide style="background-image:url('/img/bg.jpg	')"]        
## 语法基础知识(续)
----

* 命名标识符的最好的方式就是让你或者其它开发者，能很快明白它的意思: {:&.build} 
         
    ```javascript
        
        // Valid identifier names.
        var myAwesomeVariable = "a";
        var myAwesomeVariable2 = "b";
        var my_awesome_variable = "c";
        var $my_AwesomeVariable = "d";
        var _my_awesome_variable_$ = "e";
                      
    ```

[slide style="background-image:url('/img/bg.jpg	')"]        
## 语法基础知识(续)
----

* 变量定义.变量定义可以使用多个var语句，或者在单个合并var语句来定义: {:&.build} 
         
    ```javascript
        // 合法:
        var test = 1;
        var test2 = function() { ... };
        var test3 = test2( test );
        // 也合法:
        var test4 = 1,
            test5 = function() { ... },
            test6 = test2( test );
    ```
* 变量可以在不给他们分配一个值来声明。没有值声明的变量的值是undefined。 
    ```javascript
        var x;
        x === undefined; // true
    ```

[slide style="background-image:url('/img/bg.jpg	')"]        
## 类型
----

* 在JavaScript类型分为两类：基本类型和对象。基本类型包括： {:&.build} 
* String
* Number
* Boolean
* null
* undefined

[slide style="background-image:url('/img/bg.jpg	')"]        
## String
----

* 字符串是文本包裹在单引号或双引号。这是最好的做法是始终使用一个或另一个。
  有时可能当字符串中包含有用于创建字符串的引号时,
  在这种情况下，无论是使用\反斜杠转义字符，还是另一个引号，都可以。： {:&.build} 
    ```javascript
        // Strings can be created with double or single quotes.
        var a = "I am a string";
        var b = 'So am I!';
        // Sometimes a string may contain quotation marks.
        var statement1 = 'He said "JavaScript is awesome!"';
        var statement2 = "He said \"JavaScript is awesome!\"";
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Number
----

* 数值类型是任意的正的或负的数值。整数和浮点值之间没有任何区别： {:&.build} 
    ```javascript
        // Numbers are any whole or floating point integer.
        var num1 = 100;
        var num2 = 100.10;
        var num3 = 0.10;
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Boolean
----

* 布尔类型值是true或false。： {:&.build} 
    ```javascript
        // Boolean values.
        var okay = true;
        var fail = false;
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## null and undefined
----

* null和undefined是特殊类型的JavaScript。
  null类型是表示值为空的，类似于许多其他编程语言的null。
  undefined类型代表没有被分配值。这种类型以两种方式建立的：通过使用undefined关键字或根本给定值。： {:&.build} 
    ```javascript
        // Define a null value.
        var foo = null;
         
        // Two ways to achieve an undefined value.
        var bar1 = undefined;
        var bar2;
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Objects
----

* 除了以上基本类型，所有其它都是对象，我们这里将设计到以下内容： {:&.build} 
* Object
* Array
* Function
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Object
----

* 创建一个对象，最简单的方法是既可以通过对象的构造函数或称为对象文字的简写语法。
 这些简单的对象是无序的键/值对。属性值可以是任何有效的JavaScript类型，
 甚至另一个对象。创建或访问一个对象的属性，我们使用了被称为“点号”或“括号符号。” {:&.build} 
    ```javascript
        // Creating an object with the constructor:
        var person1 = new Object;
        person1.firstName = "John";person1.lastName = "Doe";
        alert( person1.firstName + " " + person1.lastName );
        // Creating an object with the object literal syntax:
        var person2 = {
            firstName: "Jane",
            lastName: "Doe"
        };
        alert( person2.firstName + " " + person2.lastName );
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Array
----

* 一个数组是一个包含多个对象的对象。
  索引从零开始，length是数组的属性。类似于一个基本对象，数组可以使用Array构造函数或称为数组的简写语法来创建。 {:&.build} 
    ```javascript
        // Creating an array with the constructor:
        var foo = new Array;
        // Creating an array with the array literal syntax:
        var bar = [];
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Array（续）
----

* Array的常用方法。 {:&.build} 
    ```javascript
        // Using the push(), pop(), unshift() and shift() methods on an array.
         
        var foo = [];
        foo.push( "a" );
        foo.push( "b" );
         
        alert( foo[ 0 ] ); // a
        alert( foo[ 1 ] ); // b
         
        alert( foo.length ); // 2
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Array（续）
----

* Array的常用方法（续）。 {:&.build} 
    ```javascript
        foo.pop();
                 
        alert( foo[ 0 ] ); // a
        alert( foo[ 1 ] ); // undefined
         
        alert( foo.length ); // 1
         
        foo.unshift( "z" );
         
        alert( foo[ 0 ] ); // z
        alert( foo[ 1 ] ); // a
         
        alert( foo.length ); // 2
        
    ```
    
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Array（续）
----

* Array的常用方法（续）。 {:&.build} 
    ```javascript
        foo.shift();
        alert( foo[ 0 ] ); // a
        alert( foo[ 1 ] ); // undefined
         
        alert( foo.length ); // 1
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## Function
----

* Function 定义。 {:&.build} 
    ```javascript
        var func_a=function(){
          alert("func_a")
        }
        
        function func_b(){
          alert("func_b")
        }
        
    ```
    
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 运算
----

* 基本运算。 {:&.build} 
    
    ```javascript
       var foo = "hello";
       var bar = "world";
       console.log( foo + " " + bar ); // "hello world"
       // Multiplication and division
       2 * 3;
       2 / 3;
       // Incrementing and decrementing
       var i = 1;
       console.log( ++i ); // 2 - because i was incremented before evaluation
       console.log( i );   // 2
       var i = 1;
       console.log( i++ ); // 1 - because i was evaluated to 1 and _then_ incremented
       console.log( i );   // 2
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 运算
----

* 对数字和字符串操作。 {:&.build} 
    
    ```javascript
       // Addition vs. Concatenation
       var foo = 1;
       var bar = "2";
       console.log( foo + bar ); // 12
       
       // Coercing a string to act as a number.
       var foo = 1;
       var bar = "2";
        
       console.log( foo + Number(bar) ); // 3

    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 运算
----

* 逻辑运算符.逻辑运算符使用AND（&&）和OR（| |）运算。。 {:&.build} 
    
    ```javascript
       var foo = 1;
       var bar = 0;
       var baz = 2;
       // returns 1, which is true
       foo || bar;
       // returns 1, which is true
       bar || foo;
       // returns 0, which is false
       foo && bar;

    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 比较操作符
----

* 逻辑运算符.逻辑运算符使用AND（&&）和OR（| |）运算。。 {:&.build} 
    
    ```javascript
       var foo = 1;
       var bar = 0;
       var baz = "1";
       var bim = 2;
       foo == bar; // false
       foo != bar; // true
       foo == baz; // true; but note that the types are different
       foo === baz;             // false
       foo !== baz;             // true
       foo === parseInt( baz ); // true
       foo > bim;  // false
       bim > baz;  // true
       foo <= baz; // true

    ```

[slide style="background-image:url('/img/bg.jpg	')"]        
## 条件代码
----

* 逻辑运算符.逻辑运算符使用AND（&&）和OR（| |）运算。。 {:&.build} 
    
    ```javascript
       var bar = false;
        
       if ( bar ) {
           // This code will never run.
           console.log( "hello true!" );
       }else{
           console.log( "hello false!" );
       }

    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 条件代码
----

* 值得真假。 {:&.build} 
    
    ```javascript
       // Values that evaluate to false:
       false
       "" // An empty string.
       NaN // JavaScript's "not-a-number" variable.
       null
       undefined // Be careful -- undefined can be redefined!
       0 // The number zero.
       // Everything else evaluates to true, some examples:
       "0"
       "any string"
       [] // An empty array.
       {} // An empty object.
       1 // Any non-zero number.

    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 条件代码
----

* 三元表达式。 {:&.build} 
    
    ```javascript
       // Set foo to 1 if bar is true; otherwise, set foo to 0:
       var bar="";
       var foo = bar ? 1 : 0;
       console.log(foo);

    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 条件代码
----

* Switch 语句。 {:&.build} 
    
    ```javascript
       var foo="";
       switch ( foo ) {
           case "bar":
               alert( "the value was bar -- yay!" );
               break;
           case "baz":
               alert( "boo baz :(" );
               break;
           default:
               alert( "everything else is just ok" );
       }

    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 循环
----

* for 语句。 {:&.build} 
    
    ```javascript
        for ( var i = 0; i < 5; i++ ) {
            
            console.log( "try " + i );
        }
    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 循环
----

* while 语句。 {:&.build} 
    
    ```javascript
        var i = 0;
        while ( i < 100 ) {
            console.log( "Currently at " + i );
            i++; 
        }
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 循环
----

* do-while 语句。 {:&.build} 
    
    ```javascript
        do {
            alert( "Hi there!" );
        } while ( false );
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 循环
----

* break and continue 语句。 {:&.build} 
    
    ```javascript
        for ( var i = 0; i < 10; i++ ) {
            if ( i==5 ) {
                break;
            }
            console.log(i);
        }
        for ( var i = 0; i < 10; i++ ) {
            if ( i==5 ) {
                continue;
            }
            console.log(i);
        }
        
    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 数组的方法和属性
----

* .length。 {:&.build} 
    
    ```javascript
        // Length of an array
         
        var myArray = [ "hello", "world", "!" ];
         
        console.log( myArray.length ); // 3
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 数组的方法和属性
----

* .join()。 {:&.build} 
    
    ```javascript
        var myArray = [ "hello", "world", "!" ];
         
        // The default separator is a comma.
        console.log( myArray.join() );     // "hello,world,!"
         
        // Any string can be used as separator...
        console.log( myArray.join( " " ) );  // "hello world !";
        console.log( myArray.join( "!!" ) ); // "hello!!world!!!";
         
        // ...including an empty one.
        console.log( myArray.join( "" ) );   // "helloworld!"
        
    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 数组的方法和属性
----

* .join()。 {:&.build} 
    
    ```javascript
        var myArray = [ "hello", "world", "!" ];
         
        // The default separator is a comma.
        console.log( myArray.join() );     // "hello,world,!"
         
        // Any string can be used as separator...
        console.log( myArray.join( " " ) );  // "hello world !";
        console.log( myArray.join( "!!" ) ); // "hello!!world!!!";
         
        // ...including an empty one.
        console.log( myArray.join( "" ) );   // "helloworld!"
        
    ```
[slide style="background-image:url('/img/bg.jpg	')"]        
## 数组的方法和属性
----

* .reverse()。 {:&.build} 
    
    ```javascript
        var myArray = [ "world" , "hello" ];
        var newArray=myArray.reverse(); // [ "hello", "world" ]
        console.log(newArray);
        
    ```
    
[slide style="background-image:url('/img/bg.jpg	')"]        
## 作业
----

* 在上一堂作业的基础上，添加渐入渐出计数器。
    
    
    
    