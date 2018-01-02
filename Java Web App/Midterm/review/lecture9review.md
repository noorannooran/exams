# Midterm Review
## Lecture 7: Cookies

### Background info
- cookie: small amount of info sent from server-> browser, then back

#### Uses:
- authentication
- user tracking
- user prefs

#### Composition
- name/value pair

### Pros and Cons
#### Cons
- Not secure
  - servers remember previous action
  - can link your information to other actions
  - can share your information
  - poorly designed sites will store credit cards

#### Code
- dont put sensitive info in cookies
- dont build servlets that depend on cookies


### Using Cookies
	- Create a cookie object
	- set max age
	- put cookie in response
	
### Reading cookies
	- request.getCookies
	  - array of cookie objects
	  
### Session vs persistent cookies
- temp  VS hard drive
- erased when browser closed VS erased once max age expires
- short lived VS long lives

- session cookies do not have a max age

### Replacing a cookie
- create a cookie with the same name and a different cookie value
- response.addCookie()


