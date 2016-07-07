cas单点登录框架：

DUBBO是一个分布式服务框架

apollo: 消息代理转发

AXIS2

Apache CXF 是一个开源的 Services 框架

RPC

F5硬件负载均衡器

JAX-RS：使用注解来简化web服务的客户端和服务器端的开发。

数据库： Druid

工具：

HttpWatch是强大的网页数据分析工具

firebug

spring boot:

groovy:

maven

gradle

RESTful一种软件架构模式

log4j

kafka

zookeeper

jdom jaxen

easymock

quartz

freemarker

checkstyle

postgresql的优势: https://wiki.postgresql.org/images/4/4c/%E5%94%90%E6%88%90_PostgreSQL_VS_MySQL_%26_oracle.pdf

ActiveMQ




开发笔记：

struts2最好别用最新的版本，否则有可能出现XXClassNotFound的情况，下载的压缩包里面有可以参考的xml文件

eclipse跑程序的时候要注意有可能因为页面缓存导致不显示新页面




maven：

struts.xml等文件的路径可以参考发布在tomcat中的项目来进行调整

注意groupId的含义包，比如:  <groupId>org.postgresql</groupId>是正确的，而<groupId>postgresql</groupId>是错误的，可以在maven的仓库查找时判断

JDBC 连接池 org.apache.tomcat.jdbc.pool 是 Apache Commons DBCP 连接池的一种替换或备选方案

spring boot:

内置tomcat,可直接打包成jar文件运行

pom.xml配置版本是可以直接使用范围表示

application.properties文件放到main下的resource目录




问题处理：

org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaAutoConfiguration': Injection of autowired dependencies failed;

将pom.xml文件引入的spring-boot-starter-data-jpa去掉就可以了


出现某些标注无法识别的时候，更新一下版本也许就能解决了

Missing artifact javax.transaction:jta:jar:1.0.1B： 查看本地的maven仓库发现明明存在但是就找不到，讲该文件多余点的后缀去掉就可以咯

java.util.concurrent.ExecutionException: org.apache.catalina.LifecycleException: Failed to start component [StandardEngine[Catalina].StandardHost[localhost].StandardContext[/ssh]]：将maven的本地仓库清空，然后再update一下项目

8200:

导入多个文件时最好使用通配符

两个子网站融合？




ssh:

@Autowired使用前要事先在applicationContext.xml文件中添加：


http://my.oschina.net/799835984/blog/540242 //自动为项目添加web.xml


spring管理action时要在pom.xml中添加： org.apache.struts struts2-spring-plugin 2.3.4.1


并在struts.xml加上：<constant name="struts.objectFactory" value="spring" />


struts.xml中这里的class值要写applicationContext.xml中改bean的id同名，而不是class的完整路径名


eclipse反向工程失败：
    org.hibernate.console.HibernateConsoleRuntimeException: Received a NoClassDefFoundError
    解决办法：创建hibernate的时候试一下其它版本的hibernate


java.lang.ClassNotFoundException: org.apache.struts2.dispatcher.ng.filter.StrutsPrepareAndExecuteFilter


    问题在于eclipse并没有将项目中的lib发布到tomcat目录下，解决办法：

    右键项目选属性，选deployment xx，添加相应的lib，如果没有找到相应的lib，那么要先在Java build path相应选项打钩

    这么好像不行：
        Go to the Markers tab (If you can't see, do Windows > Show View > Markers)
        Expand "Classpath Dependency Validator Message"
        Right click "Classpath entry org.eclipse.jdt.USER_LIBRARY/struts2 will not be exported or published. Runtime ClassNotFoundExceptions may result."
        Click "Quick Fix"
        Select "Mark the associated raw classpath entry as a publish/export dependency."
        click "Finish"

org.hibernate.HibernateException: Could not parse configuration: /hibernate.cfg.xml
Caused by: org.dom4j.DocumentException: Connection timed out: connect Nested exception: Connection timed out: connecthibernate-configuration-3.0.dtd : 文档类型声明包含或指向的标记声明必须格式正确

    原因：hibernate.cfg.xml中引用了错误的DTD文件路径“http://www.hibernate.org/dtd/hibernate-configuration-3.0.dtd”。
    解决方法：替换为正确的DTD路径：“http://hibernate.sourceforge.net/hibernate-configuration-3.0.dtd”。


The web application [vms] appears to have started a thread named [C3P0PooledConnectionPoolManager[identityToken->2s53ws9h1h6kkylepgtev|76d6ba06]-HelperThread-#2] but has failed to stop it



参考：

整合：http://www.cnblogs.com/jyh317/p/3751412.html




