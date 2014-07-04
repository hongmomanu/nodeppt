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
* 运行测试
* 运行一个REPL（你不需要再关心如何将依赖加入classpath)
* 编译Java源码（如果有的话）
* 运行项目（如果项目是一个app的话）
* 为项目产生一个Maven风格的pom文件
* 部署，编译和打包项目
* 发布类库到Maven仓库，例如Clojars  
    

[slide]

# 封面样式2 {:&.flexbox.vleft}
## 左对齐

[slide style="background-image:url('/img/bg1.png')"]

# 背景图片 {:&.flexbox.vleft}
## 使用方法：&#91;slide style="background-image:url('/img/bg1.png')"&#93;

[slide]
## 使用.class/#id/自定义属性样式
----

```html
使用：.class{:.class}
使用：#id{:#id}
组合使用：{:.class.class2 width="200px"}
父元素样式：{:&.class}
```

[slide]

## 主页面样式
### ----是上下分界线
----

nodeppt是基于nodejs写的支持 **Markdown!** 语法的网页PPT

nodeppt：https://github.com/ksky521/nodePPT

[slide]

## 这是一个列表
---

* 列表支持淡入淡出 {:&.build}
    * 上下左右方向键翻页 {:&.build}
    * 支持多级列表
    * 使用方法，markdown列表第一条加上：{:&.build}
* 完全基于markdown语法哦

[slide]
## 表格示例
### 市面上主要的css预处理器：less\sass\stylus
---
 |less| sass | stylus
:-------|:------:|-------:|--------
环境 |js/nodejs | Ruby | nodejs
扩展名 | .less | .sass/.scss | .styl
特点 | 老牌，用户多，支持js解析 | 功能全，有成型框架，发展快 | 语法多样，小众
案例/框架 | [Bootstrap](http://getbootstrap.com/) | [compass](http://compass-style.org) [bourbon](http://bourbon.io) |

[slide]

## 代码格式化
### 使用 **highlightjs**
----

```javascript
(function(window, document){
    var a = 1;
    var test = function(){
        var b = 1;
        alert(b);
    };
    //泛数组转换为数组
    function toArray(arrayLike) {
        return [].slice.call(arrayLike);
    }
}(window, document));
```
[slide]
## 支持 HTML 语法插入
----
[code]
<div class="file-setting">
    <p>这是html</p>
</div>
<p id="css-demo">这是css样式</p>
<p>使用&#91;code]&#91;/code]包裹的代码，会直接插入到页面</p>
<p>具体看下项目中 ppts/demo.md 代码</p>
<script>
    function testScriptTag(){

    }
    console.log(typeof testScriptTag);
</script>
<style>
#css-demo{
    color: red;
}
</style>
[/code]

[slide]
## iframe
----
<iframe data-src="http://www.google.com/doodle4google/resources/history.html" src="about:blank;"></iframe>

[slide]

## 居中图片
----
{:.flexbox.vcenter}

![FEinit帮助界面](https://raw.github.com/ksky521/FEinit/master/pic/feinit.png "FEinit帮助界面")

npm install -g feinit

[slide]
[note]
##这里是note

使用n键，才能显示
[/note]
## 使用note笔记
### note笔记是多窗口，或者自己做一些笔记用的
---
按下键盘【n】键测试下note，

markdown语法如下：
```markdown
[note]
这里是note，{ 要换成中括号啊！！
{/note]
```
[slide]

## 使用画笔
### 使用画笔做标记哦~你也可以随便作画啊！
---
按下键盘【p】键。按下鼠标左键，在此处乱花下看看效果。

按下键盘【c】键。清空画板

[slide]

## 使用宽屏模式
---
按下键盘【w】键。看下效果。

再按下键盘【w】键。

[slide]
## 使用overview模式
---
按下键盘【o】键。看下效果。

在overview模式下，方向键下一页，【enter】键进入选中页

或者按下键盘【o】键，退出overview模式

[slide]

## 多窗口演示
## 双屏演示不out！
---
本页面网址改成 url?_muliscreen=1，支持多屏演示哦！

跟powderpoint一样的双屏功能，带有备注信息。

[slide]
## 多种转场动画随心换
----
支持的动画包括：

 * horizontal3d
 * horizontal
 * vertical3d
 * zoomin
 * zoomout
 * cards

当然你可以自己写更炫的动画啊，记得[fork](https://github.com/ksky521/nodePPT)代码然后push给我哦~

[slide data-transition="zoomin"]

## 这是一个zoomin的动画
----
使用方法：

&#91;slide data-transition="zoomin"&#93;

[slide data-transition="vertical3d"]

## 这是一个vertical3d的动画
----
使用方法：

&#91;slide data-transition="vertical3d"&#93;

[slide data-outcallback="outcallback" data-incallback="incallback" ]
## 使用回调
----
使用方法：

&#91;slide data-outcallback="outcallback" data-incallback="incallback"&#93;

即：

 * 进入执行回调incallback函数
 * 退出执行outcallback函数

[slide]
## 设置slide？
### 修改 markdown 文件头部内容
----

``` javascript
title: nodeppt markdown 演示 //演讲主题名字
speaker: Theo Wang //演讲者名称
url: https://github.com/ksky521/nodePPT //网址
transition: zoomin //通用动画名称，可在
files: /js/demo.js,/css/demo.css //引入的文件，在页面底部
```
[slide]

## 更多玩法
---
https://github.com/ksky521/nodePPT

什么？这些功能还不够用？

极客模式：查看源码的nodeppt.js，相信你会找到牛逼的手机互动（摇一摇换页）功能

查看项目目录ppts获取更多帮助信息
