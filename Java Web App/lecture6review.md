# Midterm Review
## Lecture 6

### HTTP Response Headers
- HTTP GET request
  - has ?color=dark for example
- HTTP response
  - HTTP post reponse: HTTP/1.1 200 OK

#### things you can do with headers
- excel spreadsheet
- caching page for later use
- setting content type

#### If Cached
- client requests file
- server checks if modified since cache
- file is NOT modified, browser shows the cached version

### User Servlet to generate JPEG
- create BufferedImage
- Draw into the BufferedImage
- set content type of response header
- get an output stream
- send buffered image to output stream

### ImageServlet Example
- use ImageIO to return an image from servlet
  - set contentType of http to image/jpeg
  
