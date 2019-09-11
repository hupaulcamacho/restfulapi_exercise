# Todos API

### Root https://fsw62-todos-api.herokuapp.com/api

### Resources
* users
* todos

### Endpoints

#### Users
| Method | Endpoint                 | 
|--------|--------------------------|
| `GET`  | `/users`                 |
| `GET`  | `/users/<user-username>` |
| `POST` | `/users/signup`          |

#### Todos
| Method   | Endpoint           | Possible Query Params |
|----------|--------------------|-----------------------|
| `GET`    | `/todos`           | `username=<username>`, `completed=<true\|false>`
| `POST`   | `/todos`           ||
| `GET`    | `/todos/<todo-id>` ||
| `PUT`    | `/todos/<todo-id>` ||
| `PATCH`  | `/todos/<todo-id>` ||
| `DELETE` | `/todos/<todo-id>` ||


## Tasks
1. Try out all the requests that are possible with this API. For all the possible requests create a list like the following.
Separate requests by a long line of underscores.
    * **Request**: METHOD - ENDPOINT
    * **Body** (if applicable POST/PUT/PATCH)
    ```json
      {
        "owner": "alejo4373",
        "text": "1st Todo"
      }
    ```
    * **Response**:
    ```json
    {
      "userId": 1,
      "id": 1,
      "title": "delectus aut autem",
      "completed": false
    }
    ```
    * **What does it do?**: EXPLAIN WHAT THE REQUEST DID/DO IN PLAIN ENGLISH

MY RESPONSES:
______________________________________________________________________________________________
Users Requests

GET

   * **Request**: GET - /users
    * **Body** (if applicable POST/PUT/PATCH)
   
    * **Response**:
    ```json
{
    "payload": [
        {
            "id": 1,
            "username": "alejo4373"
        },
        {
            "id": 2,
            "username": "JRJRocks"
        },
        {
            "id": 3,
            "username": "Mike923"
        },
        {
            "id": 4,
            "username": "3Chainz"
        },
}
    ```
    * **What does it do?**: This request gets a list of created users


POST

   * **Request**: POST - /users
    * **Body** (if applicable POST/PUT/PATCH)
    * **Response**:
    ```json
    {
    "payload": {
        "user": {
            "id": 43,
            "username": "baconeggandcheese"
        },
        "msg": "User created"
    },
    "err": false
    }

    ```
    * **What does it do?**: This request created a new user with the username provided
______________________________________________________________________________________________


Todos requests

GET

   * **Request**: GET - /todos
    * **Body** (if applicable POST/PUT/PATCH)
   
    * **Response**:
    ```json
{
    "payload": [
        {
            "id": "0d0fce60",
            "owner": "kitkatjewels",
            "text": "I am awake now!",
            "completed": true
        },
        {
            "id": "1234567890",
            "owner": " Aransa",
            "text": "BONJOUR HALLO HELLO CIAO OK",
            "completed": false
        },
        {
            "id": "5b26e2d0",
            "owner": "baconeggandcheese",
            "text": "one word",
            "completed": false
        },
}
    ```
    * **What does it do?**: This request gets a list of owners and text inputs

POST

   * **Request**: Post - /todos
   * **Body** (if applicable POST/PUT/PATCH)
    ```
   {
    owner:baconeggandcheese
    text:one word
   }
   ```
    * **Response**:
    ```json
  {
      "id": "5b26e2d0",
      "owner": "baconeggandcheese",
      "text": "one word",
      "completed": false
  }
    ```
    * **What does it do?**: This request gets a list of owners and text inputs

GET

* **Request**: GET - /todos/<todos-id>
    * **Body** (if applicable POST/PUT/PATCH)
   
    * **Response**:
    ```json
    {
        "payload": {
            "id": "5b26e2d0",
            "owner": "baconeggandcheese",
            "text": "one word",
            "completed": true
        },
        "err": false
    }
    ```
    * **What does it do?**: This request gets the key value pairs from one entry

PUT

* **Request**: Put - /todos/<todo-id>
   * **Body** (if applicable POST/PUT/PATCH)
   ```  
  {
    owner:baconeggandcheese
    text:still one word
    id:5b26e2d0
    completed:true
  }
   ```
    * **Response**:
    ```json
  {
    "payload": {
        "id": "5b26e2d0",
        "owner": "baconeggandcheese",
        "text": "still one word",
        "completed": true
    },
    "err": false
  }
    ```
    * **What does it do?**: This request gets a list of owners and text inputs

PATCH
* **Request**: Patch - /todos/<todo-id>
   * **Body** (if applicable POST/PUT/PATCH)
    {  ```  
    text:Will never not be one word
    id:5b26e2d0
    completed:true
    }
    ```
    * **Response**:
    ```json
    {
    "payload": {
        "id": "5b26e2d0",
        "owner": "baconeggandcheese",
        "text": "Will never not be one word",
        "completed": true
    },
    "err": false
    }
    
    ```
    * **What does it do?**: This request changes a specific input specified by the request



DELETE

* **Request**: Delete - /todos/<todo-id>
   * **Body** (if applicable POST/PUT/PATCH)
    ```  
    
    ```
    * **Response**:
    ```json
    {
    "payload": {
        "id": "5b26e2d0",
        "owner": "baconeggandcheese",
        "text": "Will never not be one word",
        "completed": true
    },
    "err": false
    }
    
    ```
    * **What does it do?**: This request deletes the input specified by the ID number



2. Find as much status codes as possible. I will tell you how many there are by the end.

200
404

### Bonuses
1. Take a look at the next lesson to learn how to make make network requests with Javascript.
Since you previously had build a simple Todos App with HTML and now you know how to manipulate
the DOM, add some JS to try to connect that app to this API so that todos you enter in the page 
are saved to the API. Marking a todo as complete or uncompleted should work.
2. Find the easter egg.
