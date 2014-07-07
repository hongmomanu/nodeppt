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
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* 创建（一）  {:&.build}
		
    * 函数str： 函数 (str) 接受任意数量的参数。如果参数不是字符串则将其转换为字符串，返回创建的新字符串。如果没有参数或为nil，则返回空字符串""： {:&.build}
           
         ```clojure
                user=> (str 1)
                "1"
                user=> (str -2.5)
                "-2.5"
                user=> (str "a")
                "a"
                user=> (str "abc" 123)
                "abc123"
                user=> (str)
                ""
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* 创建（二）  {:&.build}
		
    * ```clojure
                user=> (str '(1 2 3))
                "(1 2 3)"
                user=> (str nil)
                ""
                user=> (str null)
                java.lang.Exception: Unable to resolve symbol: null in this context (NO_SOURCE_FILE:149)
                user=> (str "null")
                "null"
                user=> (str "abc " 123)
                "abc 123"
                user=> (str 123 345)
                "123345"
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* 创建（三）  {:&.build}
		
    * 其它比较少用的创建函数 print-str、println-str、pr-str、prn-str、with-out-str 
        ```clojure
                user=> (print-str "abc" 234)
                "abc 234"
                user=> (println-str "abc" 234)
                "abc 234\n"
                user=> (pr-str "abc" 234)
                "\"abc\" 234"
                user=> (prn-str "abc" 234)
                "\"abc\" 234\n"
                user=> (with-out-str "abc" 234)
                ""
                
         ```          
 

[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* string操作（一）   {:&.build}
		
    * count函数： count函数接受字符串参数时，返回字符串的字符数 
        
        ```clojure
                user=> (count)
                java.lang.IllegalArgumentException: Wrong number of args (0) passed to: core$count (NO_SOURCE_FILE:175)
                user=> (count nil)
                0
                user=> (count "abc123")
                6
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* string操作(二)   {:&.build}
		
    * subs函数： subs函数接受两个或三个参数, 第一个是字符串，第二个是一个整数偏移量，
      第三个（可选）是另一个整数偏移量。函数返回从第一个偏移量（含），
      到第二个（不含）偏移量或者结尾（如果没有第二个偏移量）截取的子字符串. 
        
         ```clojure
                user=> (subs "ithomer" 1)
                "thomer"
                user=> (subs "ithomer" 1 3)
                "th"
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----
    
* string操作(三)   {:&.build}
		
    * subs函数（续）：  
        ```clojure
                user=> (subs "ithomer" 1 (count "ithomer"))
                "thomer"
                user=> (subs "ithomer" 1 20)
                java.lang.StringIndexOutOfBoundsException: String index out of range: 20 (NO_SOURCE_FILE:0)
                user=> (subs "ithomer")
                java.lang.IllegalArgumentException: Wrong number of args (1) passed to: core$subs (NO_SOURCE_FILE:0)
         ```          

[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----    
* string操作(四)   {:&.build}
		
    * format函数： format函数用于格式化字符串。  
        ```clojure
                user=> (format "hello %s" "ithomer.net")
                "hello ithomer.net"
                user=> (format "%5d" 3)
                "    3"
                user=> (format "%-5d" 3)
                "3    "
                user=> (format "%05d" 3)
                "00003"
         ```          
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----    
* string操作(五)   {:&.build}
		
    * 检查函数：字符串检查函数 (string?) 接受一个参数，如果是字符串返回true，否则返回false   
        ```clojure
                user=> (string? "abc")
                true
                user=> (string? "123")
                true
                user=> (string? 123)
                false
                user=> (string? nil)
                false
         ```          
[slide style="background-image:url('/img/bg.jpg	')"]   
## 字符串
----    
* string操作(六)   {:&.build}
		
    * 字符检查函数(char?)接受一个参数，如果是字符类型返回true，否则返回false   
        ```clojure
                user=> (char? "abc")
                false
                user=> (char? \a)
                true
                user=> (char? 1)
                false
                user=> (char? nil)
                false
         ```          
 
 
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 关键字
----    
* 创建   {:&.build}
		
    * Keyword： 关键字是一个内部字符串; 两个同样的关键字指向同一个对象; 通常被用来作为map的key。  
        ```clojure
                user=> (keyword "foo")
                :foo
                user=> (keyword "user" "foo")
                :user/foo
                user=> (keyword nil)
                nil
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 关键字
----    
* 用法   {:&.build}
		
    * name： name函数接受一个参数，如果该参数为字符串，则直接返回该参数。如果不是字符串，则返回名称值。代码如下：   
        ```clojure
                user=> (name :foo)
                "foo"
                user=> (name "name")
                "name"
                user=> (name [1 2 3])
                ClassCastException clojure.lang.PersistentVector cannot be cast to clojure.lang.Named 
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 关键字
----    
* 检查   {:&.build}
		
    * keyword?用于检查指定的参数是否为关键字、或者是符号，是则返回true，否则返回false。   
        ```clojure
                user=> (keyword? [1 2 3])
                false
                user=> (keyword? :x)
                true
                user=> (keyword? "x")
                false
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 序列
----    
* 生成一个序列   {:&.build}
		
    *    
        ```clojure
                user=> ([1 2 3])
                [1 2 3]
                user=> (conj [1 2] 3 4)
                [1 2 3 4]
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 序列
----    
* 序列函数介绍（一）   {:&.build}
		
       
        ```clojure
                user=> (first [1 2 3])
                1
                user=> (last [1 2 3 4])
                4
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 序列
----    
* 序列函数介绍（二）   {:&.build}
		
       
        ```clojure
                user=> (nth [ 1 3] 0)
                1
                user=> (second [1 2 3 4])
                2
                
         ```          

[slide style="background-image:url('/img/bg.jpg	')"]   
## 序列
----    
* 序列函数介绍（三）   {:&.build}
		
       
        ```clojure
                user=> (take 2 [ 1 2 3 4] )
                (1 2)
                user=> (drop 2 [1 2 3 4])
                (3 4)
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## 序列
----    
* 序列函数介绍（四）   {:&.build}
		
       
        ```clojure
                user=> (concat [1 2 ] [3 4])
                (1 2 3 4)
                user=> (range 0 10)
                (0 1 2 3 4 5 6 7 8 9)
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## Maps （key-value键值对）
----    
* 创建   {:&.build}
		
       
        ```clojure
                user=> {:name "jack"}
                {:name "jack"}
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## Maps （key-value键值对）
----    
* 读取   {:&.build}
		
       
        ```clojure
                user=> (:name  {:name "jack"})
                "jack"
                user=> (get {:name "jack"} :name)
                "jack"
                
         ```          
 
[slide style="background-image:url('/img/bg.jpg	')"]   
## Maps （key-value键值对）
----    
* 修改   {:&.build}
       
        ```clojure
                user=> (assoc {:name "jack"} :name "hellojack" )
                {:name "hellojack"}
                user=> (assoc {:name "jack"} :sex "man" )
                {:sex "man", :name "jack"}
                
         ```          
 
