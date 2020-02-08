### admin: 青马班系统管理员端

---------

#### 一、项目结构目录

```markdown
admin
  |-- node_modules                  # 依赖包目录
  |-- public                             
  		|-- img
  		|-- static       
  			|-- css                 # 引入外部静态css样式（eg:boostrap.css）
  			|-- javascript          # 引入外部js文件（eg:vue.js,juery.js）
  			|-- 其他模板配置文件
  |-- src  
  		|-- assets
  		|-- components        	 	# 页面组件
  			|-- admin          			# 管理员页面
  				|-- show_admin.vue  			# "管理员页面"组件 
            |-- imcourse         		# 课程导入(import-course)页面
            	|-- batch.vue           	# "批量导入"组件
                |-- single.vue              # "逐一导入"组件
            |-- imstudent         		# 学生导入(import-student)页面
            	|-- batch.vue           	# "批量导入"组件
            	|-- single.vue              # "逐一导入"组件
            	|-- select_class.vue        # "班级选择下拉框"组件
            |-- mclass           		# 班级管理(manage-class)页面
            	|-- class.vue           	# "班级列表"组件
            	|-- student.vue           	# "班级名单"组件
            |-- mcourse           		# 课程管理(manage-course)页面
            	|-- checking.vue           	# "课程检索"组件
            	|-- search.vue           	# "课程考勤"组件
            |-- mstudent                # 学生管理(manage-student)页面
            	|-- student.vue           	# "学生信息"组件
            |-- navbar                  # 导航栏
            	|-- index.vue           	# "导航栏"组件
            |-- components              # 培养计划(plan)页面
            	|-- show_plan.vue           # 页面组件
        
  		|-- router                      # 注册路由
  			|-- index.js               
  		|-- store
  		|-- views
  			|-- admin.vue               # 管理员页面
  			|-- data         			# 数据分析页面
  			|-- home.vue         		# 首页
  			|-- imcourse.vue         	# 课程导入页面
  			|-- imstudent.vue         	# 学生导入页面
  			|-- imcourse.vue         	# 课程导入页面
  			|-- login.vue         	    # 登录页面
  			|-- mclass.vue         	    # 班级管理页面
  			|-- mcourse.vue         	# 课程管理页面
  			|-- mstudent.vue         	# 学生管理页面
  			|-- plan.vue                # 培养计划页面
  		|-- App.vue                 
  		|-- main.js
  		|-- registerServiceWorker
  |-- tests                        # 测试组件
 
```



#### 二、1.0版本介绍

- 实现了基本的静态页面，具体页面功能参考"项目目录结构"

- 页面打开时为登录页面，通过点击“确定”按钮进入管理员端首页页面；

- 运行启动命令：`npm run serve` 

  可在本地查看并调试：http://localhost:8080

- 目前存在的一些问题：

  - 未考虑浏览器兼容的问题（之后会补上），目前的调试是在chrome浏览器下进行；
  - 一些 css 样式（水平、垂直居中）等仍存在一些问题，比如某些按钮无法居中到页面中央，一些元素重叠在一起；

  - 表格中“添加”，“删除”中的逻辑并未实现，只是静态展示；
  - 项目实现过程中只执行了 `npm run serve` 命令在本地查看页面实现效果，并未进行build和test测试操作，若有需要，随后会进行补充；
  - 以上问题会在2.0版本中进行改进补充。

