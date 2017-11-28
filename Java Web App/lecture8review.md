# Midterm Review
## Lecture 8 : Session Handling

### Purpose
- keep a record of previous site information for client

### How it works
1. User sends data
2. Web Container sends request to a new thread of the servlet
3. thread finds session associated with User 
4. Servlet runs logic and returns a response

5. user A submits
6. Cntainer sends request to a new thread of servlet
7. Thread finds session, stores the answers as an attribute

8. User B enters data
9. Container sends request to a new thread
10. The thread starts a new sesion for User B and stores answers data


### Maintaining Client Server session state
1. Cookies
   - session ID
   - not all browser support cookies
2. Hidden form fields
   - hidden html form with sessionId
   - not all html elements > submit
3. URL rewriting
   - generate every URL dynamically
4. HttpSession Object
   - HttpSession interface
	 - good
 
 
### Implementing Session Tracking
1. unique identifier
   - sessionID
- session information for lookup
  - HashMap
2. Create cookie
   - store ID in cookie
   - add cookie to response
- Extract cookie
- set expiration date
- associate hash tables with request

### Java Session Management
- jsessionid
- associate browser with session object

### Basics
1. Access
   - request.getSession();
2. Look up info
   - session.getAttribute()
3. Store info
   - session.setAttribute()
4. discard session
   - session.removeAttribute()
   - session.invalidate()
	 - discard entire session
	 
### Threads
- if client has 2 browsers open, need to synchronise based on session id
- "multithreaded"
  - concurrency issues
- use "synchronized blocks"




