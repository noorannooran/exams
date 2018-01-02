# Midterm Review
## Lecture 5 : HTTP response

### Request Header
#### GET
- GET Request (says GET /select/selectBeerTaste.jsp?color=dark...etc.
- Implicit data in between
- blank line

#### POST
- says POST at top
- implicit data
- blank line
- data is passed in body instead of in the request
  - aka PAYLOAD

### Response
#### HTTP
- HTTP/1.1 200 OK
  - implic data
  - payload (explicit data)
	- blank line
	
### Status codes
- use constant for code, not int
- constant is in HttpServlet response
- names derived from standard message:
  - SC_OK
  - SC_NOT_FOUND
  - etc
- send error: wraps message inside small html doc
- send reidrect(string url) sets status code to 302, sets location response header

#### Common
- 100-199 Informational
- 200-299 Success
- 300-399 Redirection
- 400-499 Client errors
- 500-599 Server errors


#### Servlet Redirect
- makes browser do the work of redirecting
- can use relative URL
