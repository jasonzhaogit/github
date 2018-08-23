## servlet 01
* LAMP: Linux+Apache+MySQL+PHP   
>servlet是java服务器小程序，是用java编写的服务器程序，它的特点：    
1.由服务器端调用和执行的；  
2.用java语言编写；  
3.是按照servlet规范开发  

    浏览器-web容器-数据库   
       |    |     |	  		
     chrome |     |   
          tomcat  |  
                mysql
tomcat是一个免费开源的servlet容器、web服务器、jsp容器；  
tomact安装，配置环境变量；  	
tomcat运行依赖jdk环境；


## servlet 02


#### servlet生命周期  
 1.装载:servlet由相应的web容器来完成；    
 2.创建:一个servlet实例；  
 3.初始化:调用servlet的init()方法；   
 4.运行:调用servlet服务，即 service()方法；  
 5.销毁:调用servlet的destory()方法；  

三种开发servlet方法：  
> 方法1： implements Servlet  
      public class hello implements Servlet {
      @Override
      public void destroy() {
        // TODO Auto-generated method stub

      }

      @Override
      public ServletConfig getServletConfig() {
        // TODO Auto-generated method stub
        return null;
      }
      @Override
      public String getServletInfo() {
        // TODO Auto-generated method stub
        return null;
      }
      @Override
      public void init(ServletConfig arg0) throws ServletException {
        System.out.println("hello init");

      }

      @Override
      public void service(ServletRequest req, ServletResponse res) throws ServletException, IOException {
        System.out.println("service it");
        PrintWriter pw = res.getWriter();
        pw.println("hello servlet");

      }

> 方法2： extends GenericServlet    
> 方法3： extends HttpServlet  

web.xml配置写法  

    <?xml version="1.0" encoding="UTF-8"?>
    <web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd" id="WebApp_ID" version="3.1">
      <display-name>servlet</display-name>
      <welcome-file-list>
      <welcome-file>index.html</welcome-file>
      <welcome-file>index.htm</welcome-file>
      <welcome-file>index.jsp</welcome-file>
      <welcome-file>default.html</welcome-file>
      <welcome-file>default.htm</welcome-file>
      <welcome-file>default.jsp</welcome-file>
      </welcome-file-list>

     <servlet> 
      <servlet-name>hello</servlet-name>
      <servlet-class>helloservlet.hello</servlet-class>
      </servlet>
     <servlet-mapping>
      <servlet-name>hello</servlet-name>
      <url-pattern>/hello</url-pattern>
     </servlet-mapping>

      <servlet> 
      <servlet-name>hellogeneric</servlet-name>
      <servlet-class>helloGenericServlet.hellogeneric</servlet-class>
      </servlet>
     <servlet-mapping>
      <servlet-name>hellogeneric</servlet-name>
      <url-pattern>/hellogeneric</url-pattern>
     </servlet-mapping>

      <servlet> 
      <servlet-name>hellohttpservlet</servlet-name>
      <servlet-class>httpServlet.hellohttpservlet</servlet-class>
      </servlet>
     <servlet-mapping>
      <servlet-name>hellohttpservlet</servlet-name>
      <url-pattern>/hellohttpservlet</url-pattern>
     </servlet-mapping>

    </web-app>





