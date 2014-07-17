title: clojure语法学习之web框架学习
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## Luminus 框架介绍
----

* 什么是Luminus {:&.build} 
    * ""  {:&.build}
        
         ```text
        
                Luminus是基于一组轻量级库的微架构。它的目的是提供一个健壮的，可扩展的，易于使用的平台。
                Luminus使程序员可以专注于开发你的应用程序，减少web开发的复杂度。
                 
         ```

[slide style="background-image:url('/img/bg.jpg	')"]

## Luminus 框架介绍（续）
----

* 新建Luminus项目，在终端下执行如下命令 {:&.build} 
    * ""  {:&.build}
        
         ```bash
        
                lein new luminus myappname
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## Luminus 框架介绍（续）
----

* 运行Luminus项目，在终端下执行如下命令 {:&.build} 
    * ""  {:&.build}
        
         ```bash
        
                cd myappname
                lein ring server  
                or lein ring server-headless
                or lein ring server-headless 8000
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 定义 routes
----

* 所有标准的 HTTP 请求入口，都是由routes定义，如get,post 等方法 {:&.build} 
    * ""  {:&.build}
        
         ```clojure
        
                (defroutes app-routes
                  (GET "/" [] "Hello World!")
                  (POST "/hello" []  " Hello post" )
                  )
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 定义 routes （续）
----

* 获取参数 {:&.build} 
    * ""  {:&.build}
        
         ```clojure
        
                (defroutes app-routes
                  (GET "/" [name] （str "Hello World!" name))
                  )
                 
         ```
        
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 返回数据 
----

* 返回json {:&.build} 
    * ""  {:&.build}
        
         ```clojure
        
                (defroutes app-routes
                  (GET "/hellojson" [name] (resp/json {:response "ok"}))
                  (GET "/hellojson" [name] (resp/json [{:name "ok"} {:name "all right"}]))
                  )
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 返回数据(续) 
----

* 返回jsonp {:&.build} 
    * ""  {:&.build}
        
         ```clojure
        
                (defroutes app-routes
                  (GET "/hellojsonp" [name] (resp/jsonp name {:response "ok"}))
                  (GET "/hellojsonp" [name] (resp/jsonp name [{:name "ok"} {:name "all right"}]))
                  )
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 返回数据（续） 
----

* 返回xml {:&.build} 
    * ""  {:&.build}
        
         ```clojure
        
                (defroutes app-routes
                  (GET "/helloxml" [name] (resp/xml "<foo><name value=\"same\"></name></foo>"))
                  )
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作 
----

* 添加依赖 {:&.build} 
    * 首先在project.clj中添加 Korma 依赖 :  {:&.build}
        
         ```bash
        
                [korma "0.3.2"]
                 
         ```
    * 其次在project.clj中添加 数据库jdbc 依赖，如连接sqlite数据库 :  {:&.build}
        
         ```bash
        
                [org.xerial/sqlite-jdbc "3.7.15-M1"]
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作（续） 
----

* 配置数据库连接 {:&.build} 
    * 新建models文件夹，新建schema.clj文件，输入如下配置（sqlite连接）:  {:&.build}
        
         ```clojure
        
                (def db-spec-sqlite {:classname "org.sqlite.JDBC"
                                     :subprotocol "sqlite"
                                     :subname (str datapath db-store-sqlite)
                                     })
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作（续） 
----

* 新建中间逻辑操作层 {:&.build} 
    * 新建controller文件夹，新建home.clj文件（这里名字和routes统一，目的是为了使层次对应清晰），在其中写入业务操作逻辑:  {:&.build}
        
         ```clojure
        
                (defn create-user [username]
                  (resp/json {:results (db/create-user {:username username})})
                  )
                  
                  (defn select-user [username]
                                    (resp/json {:results (db/create-user {:username username})})
                                    )
                 
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作（续） 
----

* 新建数据库操作层 {:&.build} 
    * 在models文件夹中，新建新建db.clj文件，与controller中的方法对应，写入如下语句:  {:&.build}
        
         ```clojure
                (defn create-user [user]
                  (insert users
                          (values user))
                  )
                  (defn user-list [username]
                    (select users
                      (where {:username [like (str "%" station "%")]})
                      )
                    )
         ```
        
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作（续） 
----

* 定义访问入口 {:&.build} 
    * 好，万事具备，此时我们在routes定义访问入口即可:  {:&.build}
        
         ```clojure
        
                (GET "/helloadduser" [username] (home/create-user username))
                (GET "/hellouselistr" [username] (home/select-user username))
                 
         ```
[slide style="background-image:url('/img/bg.jpg	')"]
## 数据库操作（续） 
----

* 其它数据库连接配置 {:&.build} 
    * 本次演示的是sqlite数据库访问，其它数据库与此类似，如mysql:  {:&.build}
        
         ```clojure
        
                (def db-mysql {:subprotocol "mysql"
                               :subname "//10.33.5.103:3306/jopens"
                               :user "root"
                               :password "rootme"
                               })
                 
         ```
    * 其它数据库如postgis sqlserver oracle 等，我已经写好模板，详看[hvit](https://github.com/hongmomanu/hvit/blob/master/src/hvit/models/schema.clj)    

[slide style="background-image:url('/img/bg.jpg	')"]
## 项目发布 
----

* 通过lein 打包 {:&.build} 
    * 打包成独立运行的jar包:  {:&.build}
        
         ```bash
                lein ring uberjar
                 
         ```
    * 打包成web容器应用项目，如tomcat jetty weblogic 等
         ```bash
               lein ring uberwar
               
         ```      
[slide style="background-image:url('/img/bg.jpg	')"]
## 作业 
----

* 新建一个web项目 {:&.build} 
* 将前面作业的方法发布成web接口
* 补全增删改查功能（课件中已经完成增，查功能）
* 效果演示