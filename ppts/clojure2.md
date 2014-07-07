title: clojure语法学习之基本类型
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 数值类型
----

* 算术运算(一） {:&.build} 
    * 加法+：加法函数(+)接受任意数值类型的参数，返回它们的和；没有参数时返回0 {:&.build}
        
         ```clojure
        
                user=> (+)
                0
                user=> (+ 1)
                1
                user=> (+ 1 2 3 4)
                10
                 
         ```
        
        
    
   
[slide style="background-image:url('/img/bg.jpg	')"]

## 数值类型
----

* 算术运算(二） {:&.build}
		
    * 减法-：减法函数(-)接受任意数值类型的参数。如果只有一个参数，则返回它相反的数。
       当有多个参数时，返回第一个参数减去后面所有参数的结果。 {:&.build}
           
         ```clojure
        
                user=> (- 1)  
                -1  
                user=> (- 10 2)  
                8  
                user=> (- 10 2 3 4)  
                1 
                 
         ```
              
[slide]
## 引用网上的一段话，大家读一读，也许会有感觉
----

* 函数式编程是一种强调函数必须被当成第一等公民对待， 并且这些函数是“纯”的编程方式。 {:&.build}
* 这是受[lambda](http://en.wikipedia.org/wiki/Lambda_calculus)表达式启发的。
* 纯函数的意思是同一个函数对于同样的参数，它的返回值始终是一样的 — 而不会因为前一次调用修改了某个全局变量而使得后面的调用和前面调用的结果不一样。
* 这使得这种程序十分容易理解、调试、测试。它们没有副作用 — 修改某些全局变量， 进行一些IO操作（文件IO和数据库）。
* 状态被维护在方法的参数上面， 而这些参数被存放在栈(stack)上面（通常通过递归调用）， 而不是被维护在全局的堆（heap）上面。
* 这使得函数可以被执行多次而不用担心它会更改什么全局的状态。
   
   
[slide]
## 网上一段话（续）
---- 
*  在实际生活中，我们的程序是需要一定的副作用的。Haskel的主力开发Simon Peyton-Jones曾经曰。 {:&.build}
   
*  “到最后，任何程序都需要修改状态，一个没有副作用的程序对我们来说只是一个黑盒， 你唯一可以感觉到的是：这个黑盒在变热。。”
   
*  问题的关键是我们要控制副作用的范围， 清晰地定位它们，避免这种副作用在代码里面到处都是。
*  把函数当作“第一公民”的语言可以把函数赋值给一个变量，作为参数来调用别的函数， 同时一个函数也可以返回一个函数。
*  可以把函数作为返回值的能力使得我们选择之后程序的行为。
   
[slide]
## 网上一段话（续）
----   
*  接受函数作为参数的函数我们称为“高阶函数”。 {:&.build}
*  从某个方面来说，高阶函数的行为是由传进来的函数来配置的，这个函数可以被执行任意次，也可以从不执行。
* 函数式语言里面的数据是不可修改的。
* 这使得多个线程可以在不用锁的情况下并发地访问这个数据。
* 因为数据不会改变，所以根本不需要上锁。
* 随着多核处理器的越发流行，函数式语言对并发语言的简化可能是它最大的优点。
* 许多人觉得函数式语言并不比面向对象的语言难，它们只是风格不同罢了。
   




[slide]

## 最原始的Hello World
----

* 确认计算机中已安装好java {:&.build}
		
* 下载[clojure.jar](http://central.maven.org/maven2/org/clojure/clojure/1.6.0/)  

* 在cmd或终端中敲入如下代码
   
	 ```bash

		 java -jar clojure-1.6.0.jar
		 
	```
* ok,敲入最简单的	hello world 吧.
   
  ``` clojure 
   
     (println "hell world!")
  
  ```   

[slide]

## clojure项目开发利器 Leiningen
---

* 什么是Leiningen {:&.build}
    * Leiningen是一个用于自动化（构建）clojure项目的工具 {:&.build}
    * 让你更加专注于开发

* [Leiningen官网下载](http://leiningen.org/) 


[slide]

## Leiningen特性
---

* 创建新项目 {:&.build}
* 管理你的项目的依赖关系
* 运行一个REPL（你不需要再关心如何将依赖加入classpath)
* 编译Java源码（如果有的话）
* 运行项目（如果项目是一个app的话）
* 为项目产生一个Maven风格的pom文件
* 部署，编译和打包项目
* 发布类库到Maven仓库，例如Clojars  



[slide]

## Leiningen简单使用例子
---

* 创建新项目 {:&.build}

    ```bash

		 lein new app hello
		 
	```

* 运行一个REPL
    
    ```bash
   
   		 lein repl
   		 
   	```

* 运行项目

    ```bash

		 lein run
		 
	```

* 部署编译并打包项目
    
    ```bash

		 lein uberjar   //一个独立运行的jar包
		 
	```
  
[slide]
## 开发工具idea介绍
---

* idea是一个和 eclipse，netbeans等集成环境类似的工具，只是性能更好一点。 {:&.build}

* idea下载地址，可以选择[IntelIdea下载](http://www.jetbrains.com/idea/download/)

[slide]
## 课后作业
---

* 下载安装Leiningen。 {:&.build}

* 下载安装idea。

* 新建一个应用项目，并导入到idea

* 运行项目根据提示输入打印内容。

    

