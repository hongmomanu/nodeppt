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
         
[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----

* 算术运算(三） {:&.build}
		
    * 乘法函数 (*) 接受任意数值类型的参数并返回它们的乘积，如果只有一个参数，返回1。 {:&.build}
           
         ```clojure
        
                user=> (*)  
                1  
                user=> (* 1)  
                1  
                user=> (* 1 2 3)  
                6  
                user=> (* 0 1 2 3)  
                0  
                 
         ```

[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----

* 算术运算(四） {:&.build}
		
    * 除法/： 除法函数 (/) 接受任意数值类型的参数。第一个参数是分子，其他任意参数是分母。如果没有分母，则函数返回 1 / 分子，否则返回分子除以分母。 。 {:&.build}
           
         ```clojure
        
                user=> (/)
                java.lang.IllegalArgumentException: Wrong number of args (0) passed to: core$-SLASH- (NO_SOURCE_FILE:0)
                user=> (/ 2)
                1/2
                user=> (/ 2 10)
                1/5
                user=> (/ 1 2 4 6)
                1/48
                 
         ```     

[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----
                  
* 算术运算(五） {:&.build}
		
    * 除法/： 除法函数 (/) 接受任意数值类型的参数。第一个参数是分子，其他任意参数是分母。如果没有分母，则函数返回 1 / 分子，否则返回分子除以分母。 。 {:&.build}
           
         ```clojure
        
                user=> (/)
                java.lang.IllegalArgumentException: Wrong number of args (0) passed to: core$-SLASH- (NO_SOURCE_FILE:0)
                user=> (/ 2)
                1/2
                user=> (/ 2 10)
                1/5
                user=> (/ 1 2 4 6)
                1/48
                 
         ```    
                         

[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----
                  
* 算术运算(六） {:&.build}
		
    * 商quot： 商函数 (quot) 接受两个数值类型参数并返回第一个参数除以第二个参数的整数商。  {:&.build}
           
         ```clojure
        
                user=> (quot 10 3)
                3
                user=> (quot 10 -3)
                -3
                user=> (quot -10 3)
                -3
                user=> (quot 11 3)
                3
                user=> (quot 12 3)
                4
                user=> (quot -5.9 3)
                -1
                user=> (quot 15 0)
                java.lang.ArithmeticException: Divide by zero (NO_SOURCE_FILE:0)
                 
         ```
                                      
[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----
                  
* 算术运算(六） {:&.build}
		
    * 商quot： 商函数 (quot) 接受两个数值类型参数并返回第一个参数除以第二个参数的整数商。  {:&.build}
           
         ```clojure
        
                user=> (quot 10 3)
                3
                user=> (quot 10 -3)
                -3
                user=> (quot -10 3)
                -3
                user=> (quot 11 3)
                3
                user=> (quot 12 3)
                4
                user=> (quot -5.9 3)
                -1
                user=> (quot 15 0)
                java.lang.ArithmeticException: Divide by zero (NO_SOURCE_FILE:0)
                 
         ```                                      
[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----
                  
* 算术运算(七） {:&.build}
		
    * 注意：商函数quot与/函数不是等价的   {:&.build}
           
         ```clojure
        
                user=> (= (/ 4 2) (quot 4 2))
                true
                user=> (= (/ 3 2) (quot 3 2))
                false
                user=> (/ 3 2)
                3/2
                user=> (quot 3 2)
                1
                 
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]         
## 数值类型
----
                  
* 算术运算(八） {:&.build}
		
    * 取余rem： 余数函数 (rem) 接受两个数值类型参数并返回第一个参数除以第二个参数的余数   {:&.build}
           
         ```clojure
        
                user=> (rem 10 9)
                1
                user=> (rem 2 2)
                0
                user=> (rem 10 -3)
                1
                user=> (rem -10 3)
                -1
                user=> (rem -10 -3)
                -1
                 
         ```          

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(九） {:&.build}
		
    * 取模mod： 取模函数（mod）接收两个数值类型参数，如果两个参数为正整数或者同为负整数，则与rem函数返回值一致；如果其中有一个负数，则结果为rem返回值与第二个参数之和。   {:&.build}
           
         ```clojure
        
                user=> (mod 10 9)
                1
                user=> (mod 2 2)
                0
                user=> (mod 10 -3)
                -2
                user=> (mod -10 3)
                2
                user=> (mod -10 -3)
                -1
                user=> (mod 10 3)
                1
                 
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(十） {:&.build}
		
    * 增量函数inc： 函数 (inc) 接受一个数值类型参数并返回它的值加1。  {:&.build}
           
         ```clojure
        
                user=> (inc 1)  
                2  
                user=> (inc -1)  
                0  
                 
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(十一） {:&.build}
		
    * 减量函数 (dec)： 减量函数 (dec) 接受一个数值类型参数并返回它的值减1。   {:&.build}
           
         ```clojure
        
                user=> (dec 1)  
                2  
                user=> (dec -1)  
                0  
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(十二） {:&.build}
		
    * 最大函数max： 最大数函数 (max) 接受任意数值类型的参数并返回最大的。  {:&.build}
           
         ```clojure
        
                user=> (max 1 3 6 2)  
                6  
                 
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(十三） {:&.build}
		
    * 最小函数min： 最小数函数 (min) 接受任意数值类型的参数并返回最小的。  {:&.build}
           
         ```clojure
        
                user=> (min 1 3 6 2)  
                1  
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 算术运算(十四） {:&.build}
		
    * 精度函数with-precision： 精度函数with-precision针对大数据值操作的精度、小数点运算函数。  {:&.build}
           
         ```clojure
        
                user=> (with-precision 10 (/ 1 3))
                0.3333333333M
                user=> (with-precision 2 (/ 100M 3))
                33M
                user=> (with-precision 4 (/ 100M 3))
                33.33M  
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
                  
* 比较运算(一） {:&.build}
		
    * 值相等=： 值相等(=)函数接受若干参数，比较若干参数值是否相等。一个参数时，返回true。参数可以为nil。  {:&.build}
           
         ```clojure
        
                user=> (= 1)
                true
                user=> (= 1 1)
                true
                user=> (= 1 1.0)
                true
                user=> (= 1 2)
                false
                user=> (= 1 1 1)
                true
                user=> (= 1 1 2)
                false
                user=> (= nil nil)
                true
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 比较运算(二） {:&.build}
		
    * 值不同函数not=： 等价于(not (= obj1 obj2))   {:&.build}
           
         ```clojure
        
                user=> (not= 1 1)  
                false  
                user=> (not= 1 2)  
                true  
                user=> (not= 1 1.0)  
                true  
                user=> (not= true true)  
                false  
                user=> (not= true false)  
                true  
                user=> (not= true true false)  
                true 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 比较运算(三） {:&.build}
		
    * 小于 (<) ：小于函数 (<) 接受任意数值类型的参数，如果它们按升序排列返回true，否则返回false。   {:&.build}
           
         ```clojure
         
              user=> (< 5 10)  
              true  
              user=> (< 5 10 9)  
              false  
              user=> (< 1)  
              true 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 比较运算(四） {:&.build}
		
    * 大于 (>) ：大于函数 (>) 接受任意数值类型的参数，如果它们按降序排列返回true，否则返回false。    {:&.build}
           
         ```clojure
         
              user=> (> 5 2)
              true
              user=> (> 5 10)
              false
              user=> (> 5 10 9)
              false
              user=> (> 1)
              true
              user=> (> 0)
              true
              user=> (> -1)
              true 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 比较运算(五） {:&.build}
		
    * 大于等于 (>=) ：大于等于函数 (>=) 接受任意数值类型的参数，如果它们按降序排列或顺序相等返回true，否则返回false。     {:&.build}
           
         ```clojure
         
              user=> (>= 10 5 5)
              true
              user=> (>= 10 5 6)
              false
              user=> (>= 10 5 4)
              true 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 比较运算(六） {:&.build}
		
    * 小于等于 (<=) ：小于等于函数 (<=) 接受任意数值类型的参数，如果它们按升序排列或顺序相等返回true，否则返回false。     {:&.build}
           
         ```clojure
         
              user=> (<= 2 5 5)
              true
              user=> (<= 2 5 4)
              false
              user=> (<= 2 5 6)
              true 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(一） {:&.build}
		
    * 0检查zero?： 0检查函数 (zero?) 接受一个数值类型参数，如果是0返回true，否则返回false {:&.build}
           
         ```clojure
         
              user=> (zero? 0.0)
              true
              user=> (zero? 0)
              true
              user=> (zero? 1)
              false
              user=> (zero? 0.1)
              false 
                 
         ```           

[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(二） {:&.build}
		
    * 正数检查pos?： 正数检查函数 (pos?) 接受一个数值类型参数，如果是大于0返回true，否则返回false  {:&.build}
           
         ```clojure
         
              user=> (pos? -2)
              false
              user=> (pos? 1.2)
              true
              user=> (pos? 0)
              false
              user=> (pos? +0)
              false
              user=> (pos? 0.1)
              true   
         ```           


[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(三） {:&.build}
		
    * 负数检查neg?： 负数检查函数 (neg?) 接受一个数值类型参数，如果是小于0返回true，否则返回false   {:&.build}
           
         ```clojure
         
              user=> (neg? -3)  
              true  
              user=> (neg? 0)  
              false
                
         ```           


[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(四） {:&.build}
		
    * 偶数检查even?：   {:&.build}
           
         ```clojure
         
              user=> (even? 10)
              true
              user=> (even? 3)
              false
              user=> (even? 0)
              true
              user=> (even? -10)
              true
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(五） {:&.build}
		
    * 奇数检查odd?：    {:&.build}
           
         ```clojure
         
              user=> (odd? 10)
              false
              user=> (odd? 3)
              true
              user=> (odd? 0)
              false
              user=> (odd? -10)
              false
              user=> (odd? -9)
              true
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 验证函数(六） {:&.build}
		
    * 数值检查number?： 数值检查函数 (number?) 接受一个参数，如果是数值返回true，否则返回false   {:&.build}
           
         ```clojure
         
              user=> (number? 3.2)  
              true  
              user=> (number? "2")  
              false 
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 强制转换（一） {:&.build}
		
    * 强制转换支持以下类型： {:&.build}
           
         ```bash
         
              byte  Coerce to byte.   
              short  Coerce to short.   
              int  Coerce to int.   
              long  Coerce to long.   
              float  Coerce to float.   
              double  Coerce to double.   
              bigint  Coerce to BigInteger.   
              bigdec  Coerce to BigDecimal.   
              num  Coerce to Number.   
              rationalize  returns the rational value of num   
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 强制转换（二） {:&.build}
		
    * 强制转换支持以下类型： {:&.build}
           
         ```clojure
         
              user=> (double 12)
              12.0
              user=> (short 10000)
              10000
              user=> (short 1000000000)
              java.lang.IllegalArgumentException: Value out of range for short: 1000000000 (NO_SOURCE_FILE:0)
              user=> (int 22.2)
              22
                 
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 强制转换（三） {:&.build}
		
    * 强制转换支持以下类型： {:&.build}
           
         ```clojure
                user=> (long 22.2)
                22
                user=> (float 22)
                22.0
                user=> (bigint 100000000000)
                100000000000
                user=> (bigdec 100000000000)
                100000000000M
                
                
         ```           
[slide style="background-image:url('/img/bg.jpg	')"]   
## 数值类型
----
    
* 强制转换（三） {:&.build}
		
    * 强制转换支持以下类型： {:&.build}
           
         ```clojure
                user=> (num 22.22)
                22.22
                user=> (num "22.22")
                java.lang.ClassCastException: java.lang.String cannot be cast to java.lang.Number (NO_SOURCE_FILE:0)
                user=> (rationalize 22.22)
                1111/50
                user=> (rationalize 0.5)
                1/2
                
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

    

