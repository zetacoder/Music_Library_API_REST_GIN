# Music Library API REST with GIN Framework
Simple API REST to GET, POST, PUT and  DELETE music albums using Go and GIN framework. 
To test the application i used POSTMAN in order to emule GET, POST, PUT and DELETE http methods.

In order to maintain the simplicity, and show easily the HTTP requests, I made a list of ten music albums hosted in the base code. 
In the near future, i will implement a conecction with DB.

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

**We can check that the server is indeed running on the path: localhost:8080 in our browser. 
GET method used as default:**


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

**We can also use a GET Request searching for an Album by ID, using the route: "/albums/*** *id_number* ***".
For example, we can try to request the album #4:**

![get_request_6](https://user-images.githubusercontent.com/71451124/211176192-52b05cf5-4b6c-4478-8628-98127daa941e.png)

**When the SEND button is clicked, the func 'getAlbumsByID' is called by the handler of "/albums/id" route and is executed:**

![get_request_8](https://user-images.githubusercontent.com/71451124/211176290-16b9d26b-a614-42a3-9671-88bfc460f490.png)
![get_request_7](https://user-images.githubusercontent.com/71451124/211176265-b996e8a8-a96a-4b1c-86aa-8d1c76df3897.png)

**We can see that we get as a response the music album requested by its ID (4), the data and a STATUS OK:**

![get_request_5](https://user-images.githubusercontent.com/71451124/211175661-15a95d43-6b34-44ca-8316-5917bdfec1e3.png)



