# 详解Paste deploy #

**谈到WSGI** ，就免不了要了解paste，其中paste deploy是用来发现和配置WSGI应用的一套系统，对于WSGI应用的使用者而言，可以方便地从配置文件汇总加载WSGI应用（loadapp）；对于WSGI应用的开发人员而言，只需要给自己的应用提供一套简单的入口点即可。

## 基本概念 ##
- app， application  应用
- filter			 过滤器
- pipeline			 管道
- factory			 工厂函数
- composite			 组合
- type				 类型
- section			 段

### app（应用） ###
SGI服务的核心部分，用于实现WSGI服务的主要逻辑。app是一个callable object，接受的参数(environ,start_response)，这是paste系统交给application的，符合WSGI规范的参数. app需要完成的任务是响应envrion中的请求，准备好响应头和消息体，然后交给start_response处理，并返回响应消息体。

### filter(过滤器） ### 
一般用于一些准备性的工作，例如验证用户身份、准备服务器环境等。在一个filter执行完之后，可以直接返回，也可以交给下一个filter或者app继续执行。filter是一个callable object，其唯一参数是(app)，这是WSGI的application对象，filter需要完成的工作是将application包装成另一个application（“过滤”），并返回这个包装后的application。

### pipeline(管道) ###

由若干个filter和1个app组成。通过pipeline，可以很容易定制WSGI服务

### composite(复合体） ###

用于实现复杂的应用程序，可以进行分支选择。例如：根据不同的URL调用不同的处理程序





解析：

	[composite:main]    	-------------        [type:name]
	use = egg:Paste#urlmap
	/ = home
	/blog = blog
	/wiki = wiki
	/cms = config:cms.ini

该段配置定义了一个名为main，类型为composite的section，下面是section的具体配置，遵循key = value 的统一格式；

composite类型的section将URL请求分配给其他的WSGI应用。
	
	use = egg：Paste#urlmap 
使用Paste 包中的urlmap应用， urlmap是Paste提供的一套通用的composite应用，作用就是根据用户请求的URL前缀，将用户请求映射到对应的WSGI应用上。 这里的WSGI应用有： "home", "blog", "wiki", "config:cms.ini" </br>

最后一项仅仅是参考了同一目录中的另一个文件"cms.ini"

	[app:home]
	use = egg:Paste#static
	document_root = %(here)s/htdocs

	[app:wiki] 
	use = call:mywiki.main:application 
	database = sqlite:/home/me/wiki.db

app类型的section声明了一个具体的WSGI应用，调用哪个python module中的app代码则由**use值** 指定

