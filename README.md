# ToDoList 
Suggested APIs for ToDoList 

	Login  
o	Request: ~/Api/v1/todos/Login/{UserName}/{Password}
o	Request Ex: ~/Api/v1/todos/Login/Khaled/Aa@123421 
Respose 
iF Success :  "message": null,
    "isAuthenticated": true,
    "username": "khaled",
    "email": "khaled@gmail",
    "roles": ["User"],
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJraGFsZWQiLCJqdGkiOiJlNWJlY2FhYy0xMmFjLTQwZjYtYWZlZi02Y2YxMzJjMTE0MGIiLCJlbWFpbCI6ImtoYWxlZEBnbWFpbCIsInVpZCI6IjljMzU0ODBjLTNiMjctNGJkMi05YjBmLWVlMGQ0MDlhY2M4ZCIsInJvbGVzIjoiVXNlciIsImV4cCI6MTY3ODY0ODc0OCwiaXNzIjoiU2VjdXJlQXBpIiwiYXVkIjoiU2VjdXJlQXBpVXNlciJ9.4Lb_j3UqQIR_Nz5C_1uPzxdRwZVFuM_KoxHFv5yKBLY",
    "expiresOn": "2023-03-12T19:19:08Z"
Failure: if send empty value :
    "title": "Unsupported Media Type",
    "status": 415,
Failure: if send invalid password  Or Invalid UserName : 
 Email or Password is incorrect!                    Bad Request 400     
##################################################################
	Register
o	Request: ~/Api/v1/todos/Register/{UserName}/{Email}/{Password}
o	Request Ex: ~/Api/v1/todos/Login/Khaled/khaled@gmail.com/Aa@123321 
Respose 
iF Success :  "message": null,
    "isAuthenticated": true,
    "username": "khaled",
    "email": "khaled@gmail",
    "roles": ["User"]
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJraGFsZWQiLCJqdGkiOiJjMTQxMjgxOC02ZmQ2LTQzOTktYTM3OC03ZTM1YzU3MDA3NTAiLCJlbWFpbCI6ImtoYWxlZEBnbWFpbCIsInVpZCI6IjljMzU0ODBjLTNiMjctNGJkMi05YjBmLWVlMGQ0MDlhY2M4ZCIsInJvbGVzIjoiVXNlciIsImV4cCI6MTY3ODY0NjQ2OSwiaXNzIjoiU2VjdXJlQXBpIiwiYXVkIjoiU2VjdXJlQXBpVXNlciJ9.RhDcEKD8BDuQNVEu3bQohdVjEv6UThArvffKX6xOI_k",
    "expiresOn": "2023-03-12T18:41:09Z"

iF Email Or UserName:  
                                  Email is already registered! badRequest 400 
Failure: if send empty value :
     "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-80f82cebc002d33979afc336d71c686a-ff43d0ec9fbba90f-00"

Failure: if send wrongpassword : 
"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
     "title": "One or more validation errors occurred.",
     "status": 400,
      "traceId": "00-1b0b569d9e61bce597b9b5642b8d52ec-94d8119a7fa98877-00",
      "errors": {"Password": [Min len 8"]
##########################################################################################
	Log Out
o	Request: 
o	Request Ex:  
Respose 
iF Success :  

Failure: if send empty value :
	AddUserInGRole 
o	Request: ~/Api/v1/todos/AddUserInRole/{UserId}/{RoleName}
o	Request Ex: ~/Api/v1/todos/ AddUserInRole /Guid id/”User” 
Respose  
iF Success :  
    "userId": "9c35480c-3b27-4bd2-9b0f-ee0d409acc8d",
    "roleName": "Admin"               Ok 200
   
iF Success :  
User already assigned to this role     bad Request 400

Failure: if send empty value :
     "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-80f82cebc002d33979afc336d71c686a-ff43d0ec9fbba90f-00"

Failure: if send Wrong UserId  Or RoleName :   
Invalid user ID or Role     Bad Request 400

 ######################################################3
	GetAllUser
o	Request: ~/Api/v1/todos/GetAllUser
o	Request Ex: ~/Api/v1/todos/ GeAllUser
Respose  
iF Success :  "code": 200,
"status": "Success",
 "message": "Data Found",
 "data": [{}]
Failure: if Data empty:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message 
	PutUser
o	Request: ~/Api/v1/todos/PutUser/ body Application User
o	Request Ex: ~/Api/v1/todos/ PutUser
Respose  
iF Success :  
"code": 200,
"status": "Success",
"message": "Data Updated",
Failure: if Data empty or Not Find By Id:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message  
	DeleteUser
o	Request: ~/Api/v1/todos/DeleteUser/ body Application User
o	Request Ex: ~/Api/v1/todos/ DeleteUser
Respose  
iF Success :  
"code": 200,
"status": "Success",
"message": "User Deleted",
Failure: if Data empty or Not Find By Id:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message  

	GetAllItem
o	Request: ~/ api/v1/todos/GetAllItem/{pagenumber}/{pagesize}
Request Ex: https://localhost:7140/api/v1/todos/GetAllItem?PageNumber=1&PageSize=5
 With filter Or No And With Order By Or No
Respose  
iF Success :  "code": 200,
"status": "Success",
 "message": "Data Found",
 "data": [{}]
Failure: if Data empty:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message 
	GetItemById
o	Request: ~ /api/v1/todos/GetItemById/{id}
Request Ex: https://localhost:7140/api/v1/todos/GetItemById/1
With Filter Or NO
Respose  
iF Success :  
"code": 200,
"status": "Success",
"message": "Data",
Failure: if Data empty or Not Find By Id:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message 
	PutItem
o	Request: ~ /api/v1/todos/PutItem/ object Of ItemList
o	Request Ex: ~/Api/v1/todos/ PutItem/{}
Respose  
iF Success :  
"code": 200,
"status": "Success",
"message": "User Deleted",
Failure: if Data empty or Not Find By Id:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message  


	DeleteUser
o	Request: ~/Api/v1/todos/DeleteUser/ body Application User
o	Request Ex: ~/Api/v1/todos/ DeleteUser
Respose  
iF Success :  
"code": 200,
"status": "Success",
"message": "User Deleted",
Failure: if Data empty or Not Find By Id:
Code = 404,
Status = "Not Found",
Message = "Data Not Found",
Data = ex.Message  


