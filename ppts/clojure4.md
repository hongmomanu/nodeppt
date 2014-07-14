title: clojure语法学习之逻辑语法
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 语法注释
----

* 单行注释 {:&.build} 
    * ;  {:&.build}
        
         ```clojure
        
                user=> (println "hello") ;这是单行注释  
                "hello"  
                user=> (println "hello"  ;这是单行注释
                        "123"
                        )   
                "hello 123"  
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]

## 函数定义
----

* 创建函数(二） {:&.build} 
    * 简短的函数可以使用#()，%表示唯一的参数；%1、%2 ..依次表示第1、2、..个参数；%&表示所有参数，如下：  {:&.build}
        
         ```clojure
        
                user=> (#(/ % 3) 4)   ;结果为 4/3
                4/3  
                user=> (#(/ %2 %1) 3 4)   ;结果为 4/3 
                4/3  
                user=> (#(apply / %&) 3 5 7)   ;结果为3/5/7  
                3/35  
                 
         ```


[slide style="background-image:url('/img/bg.jpg	')"]        
