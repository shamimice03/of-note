# Authentication and Authorization
Authentication verifies the identity of a user or service, and authorization determines their access rights.

# Video (Jason Web Token - JWT) :
- https://www.youtube.com/watch?v=7Q17ubqLfaM 
- https://www.youtube.com/watch?v=MB9SgSYw0Gw

 JWT is used for authorization, not authentication. Authentication verifies the username and password, 
 while authorization ensures that the user making the request is authorized to access a specific system.
 
💡 Traditional session-based authorization uses cookies and session IDs stored on the server to authenticate and authorize users.

![image](https://github.com/shamimice03/of-note/assets/19708705/14133d94-4487-49be-806f-9c283b2f20e1)

## Session-based:

![image](https://github.com/shamimice03/of-note/assets/19708705/2de02bc5-1783-4731-8943-0ce1b9914e11)

![image](https://github.com/shamimice03/of-note/assets/19708705/a3ba2542-838f-4260-936f-0d512cd8d529)

## What will happen if session DB is down?

![image](https://github.com/shamimice03/of-note/assets/19708705/aa8982e0-3d9e-4952-abe0-db306fe15efa)


💡 JWT, on the other hand, uses a JSON web token to handle authorization. The token contains user information and is sent back to the client upon successful authentication.

💡 The JWT is stored on the client side (e.g., in a cookie) instead of the server, eliminating the need for server-side storage.

💡 When a client makes a request, it includes the JWT for authentication, and the server verifies the token's integrity by checking its signature.

![image](https://github.com/shamimice03/of-note/assets/19708705/52282cd7-dd8f-42e1-a925-db2970315bee)

![image](https://github.com/shamimice03/of-note/assets/19708705/c19daddc-ad2b-4b6f-9788-6f43b649da3d)


💡 JWT tokens consist of three parts: header, payload, and signature. The header contains information about the token's algorithm and type, the payload stores user data, and the signature ensures the token's integrity.

![image](https://github.com/shamimice03/of-note/assets/19708705/42454339-b48e-4acc-880d-db591a3e2028)


💡 JWT offers flexibility and scalability since the same token can be used across multiple servers without the need for centralized session storage.

## Check - https://jwt.io/

# Others:
Blog: https://www.educative.io/answers/why-should-you-use-jwts






