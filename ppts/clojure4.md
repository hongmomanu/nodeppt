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

## 语法注释
----

* 多行代码块注释 {:&.build} 
    * #_() {:&.build}
        
         ```clojure
        
                user=> (println "hello" (str "jack"))
                hello jack
                nil  
                user=> (println "hello" #_(str "jack"))
                hello
                nil
                user=> (println "hello" #_(str "jack"))
                hello
                nil 
                user=> #_(println 
                         "hello" #_(str "jack"))
                
                 
         ```


[slide style="background-image:url('/img/bg.jpg	')"]        
