# Midterm Review
## Lecture 2: servlet intro and basics
 
### Structure
1. src
	- code and packages
2. WebContent
	- web files
3. WebContent> Lib
	- External libraries
4. WebContent> WEB-INF
	- optional with servlets 3.0
	
### Annotations
- Use custom annotations
  - @WebServlet('/test1')
  - **SERVLET MAPPING**
- can also map servlet in web.xml file
- e.g.

```xml
<servlet>
	<servlet-name>Name</servlet-name>
	<servlet-class>Package.servlet<servlet-class>
</servlet>

<servlet-mapping>
	<servlet-name>Name</servlet-name>
	<url-pattern>address</url-pattern>
</servlet-mapping>
```

### Servlet life cycle
- init
  - first loaded
  - not called each time
- service()
  - called in new thread for each incoming
- doGet() doPost()
  - handle get and post requests
- destroy()
  - called when server deletes servlet instance
  
### service() method
- DO NOT OVERRIDE EVR


