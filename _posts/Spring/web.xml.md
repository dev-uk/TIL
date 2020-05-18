# web.xml

Created: May 17, 2020 9:41 PM
Tags: Setting

## web.xml이란?

Web Application의 Deployment Descriptor(배포 서술자, DD)로 XML형식의 파일.

WAS가 최초 구동할때 WEB-INF 디렉토리에 존재하는 web.xml을 읽고 웹 애플리케이션 설정을 구성한다. 설정을 위한 설정파일

## web.xml에 설정하는 내용

- ServletContext 초기 파라미터
- Session 유효시간 설정

    ```xml
    <error-page>
    	<error-code>404</error-code>
    		<location>/error.jsp</location>
    	</error-page>

    <error-page>
    	<error-code>500</error-code>
    	<location>/error.jsp</location>
    </error-page>
    ```

- Servlet/JSP 정의,매핑

    ```xml
    <servlet>
    	<servlet-name>appServlet</servlet-name>
    	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    	<init-param>
    		<param-name>contextConfigLocation</param-name>
    		<param-value>/WEB-INF/spring/servlet-context.xml</param-value>
    	</init-param>
    	<load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
    	<servlet-name>appServlet</servlet-name>
    	<url-pattern>*.do</url-pattern>
    	<url-pattern>/</url-pattern>
    </servlet-mapping>
    ```

- Mime Type 매핑
- Welcome File list
- Error Pages 처리
- 리스너/필터 설정
- 보안설정
-