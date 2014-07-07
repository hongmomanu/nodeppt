title: clojure基础
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 什么是clojure
----

* Clojure 是一套现代的Lisp语言的动态语言版，它是一个函数式多用途的语言，其语法和其他的Lisp一样，都是建立在 S-expression 之上，即”全是括号，前缀表达式”的语言 {:&.build}

* Clojure可以执行于Java虚拟机（JVM）引擎之上。

*  与其他Lisp一样，Clojure认为代码即数据。
   
[slide style="background-image:url('/img/bg.jpg	')"]

## clojure的特性和理念
----

* Clojure是一个动态类型语言 {:&.build}
		
* Clojure是运行在JVM(JDK5.0以上）的 

* Clojure是可以和java代码互操作的函数式语言 

* Clojure天然的并发特性 

* Clojure主要目标让编程变得简单，安全，可靠

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

		 lein new luminus mytestapp
		 
	```

* 运行一个REPL
    
    ```bash
   
   		 lein repl
   		 
   	```

* 运行项目

    ```bash

		 lein ring server-headless
		 
	```

* 部署编译并打包项目
    
    ```bash

		 lein ring uberjar   //一个独立运行的jar包
		 
		 lein ring uberwar   //可发布在任何java容器下的war包 ，tomcat jetty weblogic等
		 
	```
  
[slide]
## 开发工具idea介绍
---

* idea是一个和 eclipse，netbeans等集成环境类似的工具，只是性能更好一点。 {:&.build}

* idea下载地址，可以选择[IntelIdea下载](http://www.jetbrains.com/idea/download/)

[slide]
## 课后作业
---

* 下载安装idea。 {:&.build}

* 新建一个应用项目，并导入到idea

* 运行项目根据提示输入打印内容。

    

