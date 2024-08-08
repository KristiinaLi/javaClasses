## Clean Architecture
![CleanArchitecture](https://github.com/user-attachments/assets/35175bcc-71a0-4743-9439-d020dd50d1c4)

Entities or DTOs or Models

## Classes-Packages-Modules
![image (2)](https://github.com/user-attachments/assets/7c702e49-0394-4548-b979-e068f0b25b3f)

## How to divide
![image (3)](https://github.com/user-attachments/assets/f1310c78-a6ff-4fad-b67f-eafbf6965e8d)

## UserCOntroller
package com.datorium.Datorium.API.Controllers;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {
    //CRUD
    //AddUser
    //UpdateUser
    //GetUser
    //DeleteUser

    @GetMapping("/test")
    public String test(){
        return "testy testy";
    }
}

    @GetMapping("/add") //localhost:8080/test -> localhost:8080/user/test
    public int add@RequestBody User user {

    }
}
