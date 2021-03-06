# restful-jaxrs
### A simple restful web API for messaging, built using JAX-RS (Java API for RESTful Web Services)  
---  

Follow along [here](https://www.youtube.com/playlist?list=PLqq-6Pq4lTTZh5U8RbdXq0WaYvZBz2rbn).

**Environment Setup**:  
* Java 8 - Maven Project ([here's how to create a simple maven project](https://wiki.jasig.org/display/UPM32/Creating+a+Simple+Maven+Project))
* [Jessy 2.16](https://jersey.github.io/)  
* Apache Tomcat 8.5 Server
  
For all dependencies take a look [here](pom.xml)

**Header**:  
`Content-Type`: `application/json`  
**Resources**:  
* `http://localhost:8080/talk/webapi/messages`  
`http://localhost:8080/talk/webapi/messages?year=2017`  
* `http://localhost:8080/talk/webapi/profiles`  

  
Supported HTTP Methods: 
* **GET**:  
  Get all messages: `http://localhost:8080/talk/webapi/messages`  
  Output:  
  ```json
  [
    {
        "author": "nuhman",
        "created": "2017-12-12T20:32:38.983",
        "id": 1,
        "message": "hey ross! you saw the match yesterday?"
    },
    {
        "author": "ross",
        "created": "2017-12-12T20:35:38.913",
        "id": 2,
        "message": "hello.. Yea the blasters was great!! :)"
    }
  ]
  ```  
  Get message by message id: `http://localhost:8080/talk/webapi/messages/2`  where `2` is the message-id  
  Output:  
    ```json  
    {
        "author": "ross",
        "created": "2017-12-12T20:35:38.913",
        "id": 2,
        "message": "hello.. Yea the blasters was great!! :)"
    }
    ```  
* **POST**:   
  Sample Request body data:  
   ```json  
    {
        "author": "johns",
        "created": "2017-12-12T12:45:38.913",        
        "message": "HEYY :D"
    }
    ```  
  Add a new message by sending a POST request here: `http://localhost:8080/talk/webapi/messages`  
  Output:  
  ```json  
    {
        "author": "johns",
        "created": "2017-12-12T12:45:38.913",
        "id": 3,
        "message": "HEYY :D"
    }
    ```  
 * **PUT**:  
   Sample Request Body:  
   ```json  
    {
        "author": "johns",
        "created": "2017-12-12T12:45:38.913",        
        "message": "hey i just updated this text..."
    }
    ```  
    Update the message using message id: `http://localhost:8080/talk/webapi/messages/3`  
    Output:  
    ```json  
      {
          "author": "johns",
          "created": "2017-12-12T12:45:38.913",
          "id": 3,
          "message": "HEYY :D"
      }
      ```  
  * **DELETE**:  
    Delete the message using message id: `http://localhost:8080/talk/webapi/messages/3`  
    
