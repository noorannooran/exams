# Midterm Review
## Lecture 3 : Handling the Client Request- Form Data
### HTTP GET VS POST

### GET
- simplest
- ask server to GET a resource and send it back
- HTML, jpeg, PDF, etc

### POST
- can send user data
- GET+
- allow caller to request something, send form data to server

#### More
- can send info with GET
  - in the URL for example
  
### GET
#### PROS
- URLs bookmarked safely
- reloaded safely
- browser can cache results
- easier to test interactively

#### CONS
- security risk: variables are sent through url
- limited variables can be passed through = 2048 max

### POST
#### PROS
- security : not displayed in URL
- unlimited number
- URL is simpler
- special characters can be sent
- browser will not cache results

#### CONS
- page cannot be bookmarked
- performance response degraded

### When to use them
#### GET
- submitted search requests
- can pull up page again
#### POST
- higher security requests
- do not want user to bookmark


### Methods
- GET
- POST
- HEAD
- TRACE
- PUT
- DELETE
- OPTIONS
- CONNECT

### Form Data
- HTML files go in WebContent Folder

### Validating form data
- getParameter returns null
- or returns empty string
- check null, then check empty string
- Malformed: wrong format

#### Error
- always assume data is missing or in wrong format
- java error messages should never be shown to user

#### Handling
- replace values with default values
- redisplay the form

#### iMplementing this
1. same servlet present, process, present
2. one servlet present form, second process data and present results
3. jsp manually presents form, servlet or jsp process data and present result
4. jsp present form, automatically fill the fields with values obtained from object, have servlet or jsp process data and present the results

### This lecture
- has the implementation of error pages that would have been useful during lab test 1 lol
