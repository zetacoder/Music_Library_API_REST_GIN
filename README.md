# Music Library API REST with GIN Framework
Simple API REST to GET, POST, PUT and  DELETE music albums using Go and GIN framework. 
To test the application I used POSTMAN in order to emule GET, POST, PUT and DELETE http methods.

## STEP BY STEP GENERAL USE
 
### STARTING MUSIC LIBRARY

**A 10 music album library list allocated in our code.**
![music_album_list](https://user-images.githubusercontent.com/71451124/211158221-35291716-1d2a-40ae-9ba5-c3fc6df6852c.png)

### ROUTER, ROUTES AND HTTPS METHODS

**Localhost:8080 used as server; Handlers made for GET, POST, PUT and DELETE HTTP requests; Handlers, routes and funcs made using GIN:**
![router_routes_and_HTTP_methods](https://user-images.githubusercontent.com/71451124/211158644-734ad9b0-2fad-484c-891c-12023ae321d8.png)


### 1) INITILIZE SERVER LISTENING

**We run main.go in order to execute the code and run the local server:**
![initialize_server](https://user-images.githubusercontent.com/71451124/211159138-f6e1a5cc-eace-480d-9977-2e933cad6b03.png)
![initialize_server_code](https://user-images.githubusercontent.com/71451124/211159180-190d183f-558b-4f21-a065-2f3e8bb42677.png)

**We can check that the server is indeed running on the path: localhost:8080 in our browser:**
![localhost_on_browser_1](https://user-images.githubusercontent.com/71451124/211159958-08c2b363-9e2e-417f-95a0-636374221fcf.png) ![localhost_on_browser_2](https://user-images.githubusercontent.com/71451124/211159963-667ea78b-e22a-421d-b9fd-d4e727b79782.png)

### 2) GET HTTP REQUEST
**We use POSTMAN to test our API in a simply manner.**
**First, we select the GET method and set the path (localhost:8080) and SEND the request:**
![get_request_1](https://user-images.githubusercontent.com/71451124/211167743-f107083f-5716-4e34-8c77-12446bda0342.png)

**When the SEND button is clicked, the func 'getAlbums' is called by the handler of "/albums" route and is executed:**
![get_request_3](https://user-images.githubusercontent.com/71451124/211168168-9e2e4c48-e8fd-4ced-b5a6-e2c22bd90d6d.png)
![get_request_4](https://user-images.githubusercontent.com/71451124/211168169-a69eb979-be2d-4a78-a9dc-3bf3b8e912f8.png)

**We get the response from the request and we can see that we get the whole list of our music albums and STATUS 200 OK as response:**
![get_request_2](https://user-images.githubusercontent.com/71451124/211168212-3d3c6fe6-0975-42a3-b5d8-b6eb7cb6baa0.png)

**We can also use a GET Request searching for an Album by ID, using the route: "/albums/** id_number **".
For example, we can try to request the album #4:**
![get_request_6](https://user-images.githubusercontent.com/71451124/211176192-52b05cf5-4b6c-4478-8628-98127daa941e.png)

**When the SEND button is clicked, the func 'getAlbumsByID' is called by the handler of "/albums/id" route and is executed:**
![get_request_8](https://user-images.githubusercontent.com/71451124/211176290-16b9d26b-a614-42a3-9671-88bfc460f490.png)
![get_request_7](https://user-images.githubusercontent.com/71451124/211176265-b996e8a8-a96a-4b1c-86aa-8d1c76df3897.png)

**We can see that we get as a response the music album requested by its ID (4), the data and a STATUS OK:**
![get_request_5](https://user-images.githubusercontent.com/71451124/211175661-15a95d43-6b34-44ca-8316-5917bdfec1e3.png)


### 3) POST HTTP REQUEST
**Now, we´re going to POST a new Album in our library.
To do that, first we prepare the METHOD (POST), ROUTE (localhost:8080/albums) and we must fill the Body section with the NEW MUSIC ALBUM. 
In most cases, its used JSON format:**
![post_request_1](https://user-images.githubusercontent.com/71451124/211179078-f660cf20-435b-4337-94e6-49aeeedb6afc.png)

**When the request is sent, the handler for the route is executed and the function 'postAlbums' is called:**
![post_request_2](https://user-images.githubusercontent.com/71451124/211179182-036d9893-01fa-431e-9e43-100d95f5c57f.png)

**If everything went good, we can see that the New Music Album was created and added to the library with a 201 Created Status code:**
![post_request_4](https://user-images.githubusercontent.com/71451124/211179307-2555a9b6-a12d-4527-84a9-6f8002eba2aa.png)

**If we try to Post an already existing ID (#11 from the previous example), it will response with a Status 400 code:**
![post_request_5](https://user-images.githubusercontent.com/71451124/211179563-898e3b84-1bfa-4f8c-bb82-d97658a5b15b.png)

**The same response will occur if the Album name already exists:**
![post_request_6](https://user-images.githubusercontent.com/71451124/211179610-8d3d58bf-b216-4430-b74c-c9f5f5fcb287.png)

### 4) PUT HTTP REQUEST
**Now we´re going to replace an existing album with another using the ID of the Album to replace it.**
**First, we make a GET request to know the existing Music Albums. We are going to replace ID: 2, "Hybrid Theory" by Linkin Park:**
![put_request_1](https://user-images.githubusercontent.com/71451124/211210014-b1d91444-d66c-42b5-8424-357570682484.png)

**To replace that resource, we sent the new data (JSON format) in the body of the request with POST method using the same ID (2).
We can see that as response we have a 200 OK STATUS and now in the ID #2 the older album was replaced:**
![put_request_3](https://user-images.githubusercontent.com/71451124/211210831-f79f1f33-2e4a-4f1c-95a7-1776973bb265.png)

**Finally if we try to do a PUT request using a non-existing ID (p.e "99") it will throw a 400 Bad Request STATUS as shown below:**
![put_request_4](https://user-images.githubusercontent.com/71451124/211212873-391b49db-630e-4b1c-813e-4a2ca59e3aed.png)


### 5) DELETE HTTP REQUEST
**Finally, we can use DELETE Method to erase a Music Album by ID. 
First, we use GET method to see all the list:**
![delete_request_1](https://user-images.githubusercontent.com/71451124/211213217-b2671c6c-50e0-4144-b953-4464e8cff578.png)

**Lets say we want to DELETE registry with ID 3 ("Ser Humano Album"). To do that we need to specify in the route which ID element we´re going to erase.
In this case, it would be localhost:8080/albums/3**
![delete_request_2](https://user-images.githubusercontent.com/71451124/211213404-bad63eeb-882e-46b0-9599-01e61ab18251.png)

**We can see that the Album with ID 3 was erased succesfully with a 200 Status code:**
![delete_request_3](https://user-images.githubusercontent.com/71451124/211213548-a05d2036-1d0e-40ee-bd14-f7a8da38abb8.png)

**If we try to DELETE a non-existing element, for example ID #100, it will throw a 404 Not Found Status:**
![delete_request_4](https://user-images.githubusercontent.com/71451124/211213706-3db033bb-ea9d-4f0d-8fc0-c59323ebb27d.png)

## CONCLUSION
By way of conclusion we can say that using GIN framework to create a REST API application is extremely simple, useful, powerful and with few lines of code, providing the necessary functionality to deploy a server securely, handle responses to and from the client and all with the simple and elegant Golang syntax.
