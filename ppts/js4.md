title: 前端语法学习之jQuery Easyui框架介绍
speaker: Jack
url: https://github.com/hongmomanu
transition: cards
files: /js/demo.js,/css/demo.css

[slide style="background-image:url('/img/bg.jpg	')"]

## 什么是jQuery EasyUI
----

* jQuery EasyUI是一组基于jQuery的UI插件集合。 {:&.build} 
    

* jQuery EasyUI的目标就是帮助web开发者更轻松的打造出功能丰富并且外观统一的UI界面
         
* jQuery EasyUI为我们提供了大多数常用UI控件的使用，如：accordion，combobox，menu，dialog，tabs，validatebox，datagrid，window，tree等等。

[slide style="background-image:url('/img/bg.jpg	')"]    
## 使用jQuery EasyUI
----

* [官方下载最新版本1.3.6](http://www.jeasyui.com/download/index.php):  {:&.build} 
         
* 引入文件:  
         
    ```html
             
         <link rel="stylesheet" type="text/css" href="easyui1.3.6/themes/bootstrap/easyui.css">
         <script type="text/javascript" src="jquery-1.11.1.js"></script>
         <script type="text/javascript" src="easyui1.3.6/jquery.easyui.min.js"></script>
         <script type="text/javascript" src="easyui1.3.6/locale/easyui-lang-zh_CN.js"></script>
                      
    ```
、    
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## hello world
----

* 引入上述文件后，添加如下标签:  {:&.build} 
         
    ```html
         <a href="#" class="easyui-linkbutton" >Hello world!</a>
    ```
    
    
    
[slide style="background-image:url('/img/bg.jpg	')"]    
## 另一种写法
----

* 根据id，动态生成:   {:&.build} 
         
    ```javascript
          
          $('#btn2').linkbutton();  
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## 添加一个事件
----

* 两种方式，自带onClick，jquery binding:   {:&.build} 
         
    ```javascript
        
       $('#btn2').linkbutton({
         onClick:function(){
            alert("自带")
         }
       });       
       
       $('#btn2').bind('click',function(){alert('binding')});
              
    ```

[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Panel.标签方式:   {:&.build} 
         
    ```html
        
       <div id="p" class="easyui-panel" title="My Panel" 
               style="width:500px;height:150px;padding:10px;background:#fafafa;"
               data-options="iconCls:'icon-save',closable:true,
                       collapsible:true,minimizable:true,maximizable:true">
           <p>panel content.</p>
           <p>panel content.</p>
       </div>
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Panel.代码生成:   {:&.build} 
         
    ```javascript
        
      $('#panel').panel({
          width:500,
          height:150,
          title:'My Panel',
          tools:[{
              iconCls:'icon-add',
              handler:function(){alert('new')}
          },{
              iconCls:'icon-save',
              handler:function(){alert('save')}
          }]
      }); 
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Tabs.标签引入:   {:&.build} 
         
    ```html
        
      <div id="tt" class="easyui-tabs" style="width:500px;height:250px;">
          <div title="Tab1" style="padding:20px;display:none;">
              tab1
          </div>
          <div title="Tab2" data-options="closable:true" style="overflow:auto;padding:20px;display:none;">
              tab2
          </div>
          <div title="Tab3" data-options="iconCls:'icon-reload',closable:true" style="padding:20px;display:none;">
              tab3
          </div>
      </div> 
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Tabs.代码生成:   {:&.build} 
         
    ```javascript
      $('#tt').tabs({
          border:false,
          onSelect:function(title){
              alert(title+' is selected');
          }
      });
      $('#tt').tabs('add',{
          title:'新标签1',
          content:'新标签一内容',
          closable:true
      }); 
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Accordion.标签引入:   {:&.build} 
         
    ```html
        
      <div id="aa" class="easyui-accordion" style="width:300px;height:200px;">
          <div title="Title1" data-options="iconCls:'icon-save'" style="overflow:auto;padding:10px;">
              <h3 style="color:#0099FF;">Accordion for jQuery</h3>
              <p>Accordion is a part of easyui framework for jQuery. 
              It lets you define your accordion component on web page more easily.</p>
          </div>
          <div title="Title2" data-options="iconCls:'icon-reload',selected:true" style="padding:10px;">
              content2
          </div>
          <div title="Title3">
              content3
          </div>
      </div>
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* Accordion.代码动态生成:   {:&.build} 
    ```javascript
      $('#aa').accordion({
          width:200,
          height:200
      });
      $('#aa').accordion('add', {
          title: 'New Title1',
          content: 'New Content1',
          selected: true
      });
      $('#aa').accordion('add', {
          title: 'New Title2',
          content: 'New Content2',
          selected: false
      });
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* layout.标签引入:   {:&.build} 
    ```html
      
      <div id="cc" class="easyui-layout" style="width:600px;height:400px;">
          <div data-options="region:'north',title:'North Title',split:true" style="height:100px;"></div>
          <div data-options="region:'south',title:'South Title',split:true" style="height:100px;"></div>
          <div data-options="region:'east',title:'East',split:true" style="width:100px;"></div>
          <div data-options="region:'west',title:'West',split:true" style="width:100px;"></div>
          <div data-options="region:'center',title:'center title'" style="padding:5px;background:#eee;"></div>
      </div>
              
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Layout 布局
----

* layout.代码动态生成:   {:&.build} 
    ```javascript
    
      $('#cc').layout({fit:true});
      $('#cc').layout('add',{
          region: 'west',
          width: 180,
          title: 'West Title',
          split: true
      });
      $('#cc').layout('add',{
          region: 'center',
          title: 'Center Title'
      });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Form 表单
----

* form表单引入:   {:&.build} 
    ```html
    
      <form id="ff"  method="post">
          <div>
              <label for="name">Name:</label>
              <input class="easyui-validatebox" type="text" name="name" data-options="required:true" />
          </div>
          <div>
              <label for="email">Email:</label>
              <input class="easyui-validatebox" type="text" name="email" data-options="validType:'email'" />
          </div>
          ...
      </form>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Form 表单
----

* form表单提交:   {:&.build} 
    ```javascript
       
       $('#ff').form({
           url:'test',
           onSubmit: function(){
               // do some check
               // return false to prevent submit;
           },
           success:function(data){
               alert("测试")
           }
       });
       // submit the form
       $('#ff').submit();
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Form 表单
----

* form表单load数据:   {:&.build} 
    ```javascript
       $('#ff').form('load',{
       	name:'name2',
       	email:'mymail@gmail.com'
       	
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Form 表单
----

* form表单清空数据:   {:&.build} 
    ```javascript
       $('#ff').form('clear');
      
    ```

[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* window.标签引用:   {:&.build} 
    ```html
       <div id="win" class="easyui-window" title="My Window" style="width:600px;height:400px"
               data-options="iconCls:'icon-save',modal:true">
           Window Content
       </div>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* window.代码生成:   {:&.build} 
    ```javascript
       $('#win').window({
           width:200,
           height:100,
           modal:true
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* dialog.标签引入:   {:&.build} 
    ```html
       <div id="dd" class="easyui-dialog" title="My Dialog" style="width:400px;height:200px;"
               data-options="iconCls:'icon-save',resizable:true,modal:true">
           Dialog Content.
       </div>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* dialog.代码生成:   {:&.build} 
    ```javascript
       $('#dd').dialog({
           title: 'My Dialog',
           width: 400,
           height: 200,
           closed: false,
           buttons:[{
               text:'保存',
               handler:function(){alert(1);}
           },{
               text:'关闭',
               handler:function(){$('#dd').dialog('close');}
           }],
           modal: true
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* messager.alert:   {:&.build} 
    ```javascript
       
       $.messager.alert('Warning','The warning message');
      
    ```

[slide style="background-image:url('/img/bg.jpg	')"] 
## Window 窗体
----

* messager.confirm:   {:&.build} 
    ```javascript
       
       $.messager.confirm('Confirm','Are you sure you want to delete record?',function(r){
           if (r){
               alert('ok');
           }
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* DataGrid.标签引入:   {:&.build} 
    ```html
       
       <table class="easyui-datagrid" style="width:400px;height:250px"
               data-options="url:'datagrid_data.json',fitColumns:true,singleSelect:true">
           <thead>
               <tr>
                   <th data-options="field:'code',width:100">Code</th>
                   <th data-options="field:'name',width:100">Name</th>
                   <th data-options="field:'price',width:100,align:'right'">Price</th>
               </tr>
           </thead>
       </table>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* DataGrid.代码生成:   {:&.build} 
    ```javascript
       
       $('#dg').datagrid({
           url:'datagrid_data.json',
           columns:[[
               {field:'code',title:'Code',width:100},
               {field:'name',title:'Name',width:100},
               {field:'price',title:'Price',width:100,align:'right'}
           ]]
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* tree.标签引入:   {:&.build} 
    ```html
       <ul id="tt" class="easyui-tree">
           <li>
               <span>Folder</span>
               <ul>
                   <li>
                       <span>Sub Folder 1</span>
                       <ul>
                           <li><span><a href="#">File 11</a></span></li>
                       </ul>
                   </li>
                   <li><span>File 2</span></li>
               </ul>
           </li>
       </ul>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* tree.代码生成:   {:&.build} 
    ```javascript
       $('#tt').tree({
           url:'tree_data.json'
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* treegrid.标签引入:   {:&.build} 
    ```html
       
       <table id="tt" class="easyui-treegrid" style="width:600px;height:400px"
               data-options="url:'treegrid_data.json',idField:'id',treeField:'name'">
           <thead>
               <tr>
                   <th data-options="field:'name',width:180">Task Name</th>
                   <th data-options="field:'persons',width:60,align:'right'">Persons</th>
                   <th data-options="field:'begin',width:80">Begin Date</th>
                   <th data-options="field:'end',width:80">End Date</th>
               </tr>
           </thead>
       </table>
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## DataGrid and Tree 数据表格和树
----

* treegrid.代码生成:   {:&.build} 
    ```javascript
       
       $('#tt').treegrid({
           url:'treegrid_data.json',
           idField:'id',
           treeField:'name',
           columns:[[
               {title:'Task Name',field:'name',width:180},
               {field:'persons',title:'Persons',width:60,align:'right'},
               {field:'begin',title:'Begin Date',width:80},
               {field:'end',title:'End Date',width:80}
           ]]
       });
      
    ```
[slide style="background-image:url('/img/bg.jpg	')"] 
## 作业
----

* 在上次作业的基础上添加踪迹记录写入到datagrid中:   {:&.build} 

* 演示如下
    
    