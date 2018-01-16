# Midterm Review
## Lecture 4: HTTP Request Headers

### Analysis
	- Header
	- Accept
	- Accept-Encoding
	- Connection
	- Cookie
	- Host
	- Referer
	- User-Agent

### General Methods
- getHeader()
- getHeaders()
  - returns enum String obj
- getHeaderNames()
  - returns enum String header names

### Other methods
- getMethod
- getRequestURI
- getQueryString
- getProtocol

### Validation
- always check that header is non-null first

### Header explantion
#### Accept
	- MIMe types a browser can handle
	  - e.g. PNG, GIF
#### Accept-Encoding
	- indicates encoding browser can handle (gzip, etc)
#### Authroization
	- user ID for password protected pages
	- html forms send information in session object
#### Referer
	- URL of referring page
	  - tracking
#### User-Agent
	- client identifying self
	  - what kind of device
#### Host
	- host given to original URL

#### Connection
	- keep-alive: persistent connection
	- HTTP 1.1 persistent = default
	  - server can reuse socket over
#### Cookie
	- cookies prev. set to client
	
