title: clojure语法学习之逻辑语法
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 语法注释
----

* 单行注释 {:&.build} 
    * ";"  {:&.build}
        
         ```clojure
        
                hello.core=> (println "hello") ;这是单行注释  
                "hello"  
                hello.core=> (println "hello"  ;这是单行注释
                        "123"
                        )   
                "hello 123"  
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]

## 语法注释
----

* 多行代码块注释 {:&.build} 
    * "#_" {:&.build}
                  
         ```clojure
                hello.core=> (println "hello" (str "jack"))
                hello jack
                nil  
                hello.core=> (println "hello" #_(str "jack"))
                hello
                nil
                hello.core=> (println "hello" #_(str "jack"))
                hello
                nil 
                hello.core=> #_(println 
                         "hello" #_(str "jack"))
                 
         ```

[slide style="background-image:url('/img/bg.jpg	')"]

## Bindings
----

* Clojure里面是没有所谓创建变量声明的概念,它用Bindings来替代变量。包括：全局binding “def”，当前局部bingding “let”，以及宏 binding {:&.build} 
    

[slide style="background-image:url('/img/bg.jpg	')"]

## Bindings（续）
----

*   def 这个special form 定义一个全局的 binding,并且你还可以给它一个"root value",例如:
    
       ```clojure
               hello.core=> (def ^:dynamic foo 1)
               #'hello.core/foo  
       ```

[slide style="background-image:url('/img/bg.jpg	')"]

## Bindings（续）
----
        
*   那么对于变量foo来说,1是它的root binding,这个值对于所有线程可见,REPL的主线程可见:
       ```clojure
       
           hello.core=> foo
           1
                
       ```

[slide style="background-image:url('/img/bg.jpg	')"]

## Bindings（续）
----

*   启动一个独立线程查看下foo的值：
       ```clojure
              
             hello.core=>  (.start (Thread. #(println foo)))
             1
             nil
                       
        ``` 

[slide style="background-image:url('/img/bg.jpg	')"]
## Bindings（续）
----

*   但是，利用binding宏可以给var创建一个thread-local级别的binding，binding只对于持有它的线程是可见的，直到线程执行超过binding的范围为止，binding对于其他线程是不可见的。：
       ```clojure
              
             hello.core=> (binding [foo 2] foo)
             2
        ``` 

[slide style="background-image:url('/img/bg.jpg	')"]
## Bindings（续）
----

*   let和binding非常相似，两者的调用方式近乎一致：
       ```clojure
              
             hello.core=>  (let [foo 2] foo)
             2
        ``` 
                   
[slide style="background-image:url('/img/bg.jpg	')"]
## Bindings（续）
----

*   下面我们从一个例子可以看出两者的不同，定义一个print-foo函数，用于打印foo变量：：
       ```clojure
              
             hello.core=>   (defn print-foo [] (println foo))
             #'hello.core/print-foo
        ``` 
                   
[slide style="background-image:url('/img/bg.jpg	')"]
## Bindings（续）
----

*     foo不是从参数传入的，而是直接从当前context寻找的，因此foo需要预先定义。分别通过let和binding来调用print-foo,可以看到，print-foo仍然打印的是初始值1，而不是let绑定的2：
       ```clojure
              
             hello.core=> (let [foo 2] (print-foo))
             1
             nil
        ``` 

[slide style="background-image:url('/img/bg.jpg	')"]                   
## Bindings（续）
----

*      如果用binding:print-foo这时候打印的就是binding绑定的2。这是为什么呢？这是由于let的绑定是静态的，它并不是改变变量foo的值，而是用一个词法作用域的foo“遮蔽”了外部的foo的值。
       ```clojure
              
             hello.core=> (binding [foo 2] (print-foo))
             2
             nil
        ``` 
[slide style="background-image:url('/img/bg.jpg	')"]                   
## Bindings（续）
----

*   Clojure告诉你,let中的foo不是一个有效的赋值目标，foo是不可变的值。set!可以修改binding的变量：
       ```clojure
              
             hello.core=> (let [foo 2] (set! foo 3))
             CompilerException java.lang.IllegalArgumentException: Cannot assign to non-mutable: foo, compiling:(/tmp/form-init5385717729874115910.clj:1:1) 
             
             hello.core=> (binding [foo 2] (set! foo 3) (print-foo))
             3
             nil
       ``` 
                   
   
 
