cas单点登录框架：


DUBBO是一个分布式服务框架


apollo: 消息代理转发

AXIS2

Apache CXF 是一个开源的 Services 框架

RPC

F5硬件负载均衡器


JAX-RS：使用注解来简化web服务的客户端和服务器端的开发。

数据库：
	Druid


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

jdom	jaxen

easymock


quartz

freemarker


checkstyle





postgresql的优势: https://wiki.postgresql.org/images/4/4c/%E5%94%90%E6%88%90_PostgreSQL_VS_MySQL_%26_oracle.pdf


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




8200:

导入多个文件时最好使用通配符

两个子网站融合？





ssh:

@Autowired使用前要事先在applicationContext.xml文件中添加：
<bean class="org.springframework.beans.factory.annotation.AutowiredAnnotationBeanPostProcessor"/>


http://my.oschina.net/799835984/blog/540242 //自动为项目添加web.文件


spring管理action时要在pom.xml中添加：
    <dependency>
        <groupId>org.apache.struts</groupId>
        <artifactId>struts2-spring-plugin</artifactId>
        <version>2.3.4.1</version>
    </dependency>

并在struts.xml加上：<constant name="struts.objectFactory" value="spring" />

struts.xml中<action name ="index" class = "Application" method = "index">这里的class值要写applicationContext.xml中改bean的id同名，而不是class的完整路径名


参考：

整合：http://www.cnblogs.com/jyh317/p/3751412.html
