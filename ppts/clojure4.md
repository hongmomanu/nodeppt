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
                   
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制
----

*   repeatedly 字面意思为重复函数。一般的用法如下:  {:&.build}
       ```clojure
             hello.core=> (repeatedly 5 #(str 1))
             ("1" "1" "1" "1" "1")
             
       ``` 
       
*   repeat函数：repeat函数接受常量参数，用法如下:

       ```clojure
       
            hello.core=> (repeat 5 1)
            (1 1 1 1 1)
            
       ```            
   
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制(续)
----

*   当repeat、repeatedly函数只接受一个参数时（即没有重复次数的参数），需要配合take来中止，否则会产生内存溢出的错误。如下  {:&.build}
       ```clojure
             hello.core=> (repeatedly #(int 11))  
             OutOfMemoryError Java heap space 
             hello.core=> (take 5(repeatedly #(int 11)))  
             (11 11 11 11 11)
             
       ``` 

[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制(续)
----

*   iterate,迭代函数形式如(iterate f v) ,相当于while(true) { v = f(v) },所以一般要配合 take 来终止   {:&.build}
       ```clojure
             hello.core=> (take 10 (iterate inc 11))
             (11 12 13 14 15 16 17 18 19 20)
             hello.core=> (take 10 (iterate #(+ % 5) 11))  
             (11 16 21 26 31 36 41 46 51 56)
             hello.core=> (take 10 (iterate #(* % 2) 11))  
             (11 16 21 26 31 36 41 46 51 56)
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制(续)
----

*   dotimes 会执行给定的表达式一定次数, 一个本地binding会被给定值：从0到一个给定的数值。如下：    {:&.build}
       ```clojure
             hello.core=> (dotimes [num 3] (println "number:" num)) 
             number: 0
             number: 1
             number: 2
             nil
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制(续)
----

*   doseq,遍历给定的集合,并用指定的表达式以有副作用的方式执行它们, 并且返回nil     {:&.build}
       ```clojure
             hello.core=> (doseq [i (range 10)] (println i))  
             0
             1
             .
             .
             9
             nil
             hello.core=> (doseq [i (range 10) j (range 2)] (println (str i "__" j)))  
             0__0
             0__1
             1__0
             1__1
              .
              .
             9__0
             9__1
              nil
       ``` 
       
   
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 循环控制(续)
----

*   for,和doseq的语法是一样的，只不过for返回的是一个序列    {:&.build}
       ```clojure
             hello.core=>  (for [x (range 5)] (* x x))    
             (0 1 4 9 16)
             hello.core=> (for [x (range 5) y [2 3]] (* x y))    
             (0 0 2 3 4 6 6 9 8 12)
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断
----

*   if：将一个判断表达式作为它的第一个参数进行求值。如果求值为true，那么就返回它的第二个参数（相当于“then”子句）的求值结果。如果结果为false（包括nil）就返回第三个参数的求值结果（相当于“else”子句）  {:&.build}
       ```clojure
             hello.core=>  (defn is-small [number] (if (< number 100) "yes" "no"))   
             #'hello.core/is-small
             hello.core=> (is-small 50)  
             "yes"
             hello.core=> (is-small 150)  
             "no"
       ``` 
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   if条件中除了false和nil，其他都为true：   {:&.build}
       ```clojure
             hello.core=>  (if true "true" "false")  
             "true"  
             hello.core=> (if 0 "true" "false")   
             "true" 
             hello.core=> (if "" "true" "false")  
             "true"
             hello.core=> (if nil "true" "false")  
             "false" 
             hello.core=> (if false "true" "false")  
             "false"
       ``` 

[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   if-not：跟 if 的用法相同，但是作用是相反的。当逻辑为false的时候会去计算第二个参数的值，为true的时候才计算第三个参数的值 ：   {:&.build}
       ```clojure
             hello.core=>  (if-not (zero? 0) "no" "yes")  
             "yes"   
             hello.core=> (if (not (zero? 0)) "no" "yes")    
             "yes" 
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   if-let：if-let宏接受两个参数，第一个参数为绑定变量，第二个参数为表达式。并根据第二个表达式参数返回的值确定执行then、else语句。   {:&.build}
       ```clojure
             hello.core=>  (defn if-let-test [arg] (if-let [x arg] "true" "false"))    
             #'hello.core/if-let-test   
             hello.core=> (if-let-test 1)   
             "true"
             hello.core=> (if-let-test nil)   
             "false" 
             
       ```
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   when: when没有else子句，如果when后面第一个参数为true，则执行条件后的所有语句，否则返回nil。  {:&.build}
       ```clojure
             hello.core=>  (when false (println "is true") "return true")    
             nil   
             hello.core=> (when true (println "is true") "return true")   
             is true
             "return true"
             
       ``` 
       
   
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   when-not: when-not与when类似，只是第一个参数返回false，才执行后面所有语句，否则返回nil。  {:&.build}
       ```clojure
             hello.core=>  (when-not  false (println "is true") "return true")   
             is true
             "return true"   
             hello.core=> (when-not true (println "is true") "return true")   
             nil
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   cond : cond 可以有任意个“判断/表达式”对，作为它的参数。如果满足第一个判断，就执行第一个判断对应的表达式。如果没有满足第一个条件，就会尝试后面的判断表达式，以此类推。如果一个都没有满足，那么返回 nil 除非你用一个 :else 关键字放在最后来抓住剩下的所有可能性。cond类似于java中的switch..case..default语句，如：   {:&.build}
       ```clojure
             hello.core=>  (defn f [n] (cond (< n 0) "<0" (< n 10) "<10" :else ">=10"))   
             #'hello.core/f  
             hello.core=> (f -2)    
             "<0"
             hello.core=> (f 2)    
             "<10"
             hello.core=> (f 12)    
             ">=10"
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   case : case可以简单理解为java中switch的case，如下：   {:&.build}
       ```clojure
             hello.core=>  (let [mystr "hello"]
                                     (case mystr    
                                       "" 0   
                                       "hello" (count mystr)))    
             5 
             hello.core=> (let [mystr "no match"]   
                                    (case mystr    
                                          "" 0   
                                          "hello" (count mystr)   
                                          "default")) 
             "default"
             
       ``` 
       
[slide style="background-image:url('/img/bg.jpg	')"]                   
## 条件判断(续)
----

*   case可以用列表一次匹配多个值：    {:&.build}
       ```clojure
             hello.core=>  (defn f [x] (case x  
                                  (5 10 15) "5的倍数"  
                                  (3 6 9) "3的倍数"  
                                  "others"))    
             #'hello.core/f   
             hello.core=> (f 3) 
             "3的倍数"
             hello.core=> (f 5) 
             "5的倍数"
             hello.core=> (f 15) 
             "5的倍数" 
             hello.core=> (f 1) 
             "others"
             
       ``` 
       
   
 
