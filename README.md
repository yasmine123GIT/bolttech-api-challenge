# Bolttech API QA Challenge
This repository contains my solution to the Bolttech QA API automation challenge using Postman.

## What's included
- Postman collection: `Bolttech_API_QA_Challenge.postman_collection.json`
- Test cases for:
  - User registration and login (valid and invalid)
  - Employee creation, update, deletion
- Basic response validation using Postman test scripts

## 🔧 To run the API
```bash
sudo ./api_challenge-3.156.0

For this challenge : i choose Linux
1)Register a new user and log in

Register a new user
curl -X POST http://localhost:5000/api/register \
  -F "email=yasmine_mahfoudhi@gmail.com" \
  -F "password=Yasmine@123" \
  -F "role=admin"

Login:
curl -X POST http://localhost:5000/api/login \
     -u yasmine_mahfoudhi@gmail.com:Yasmine@123 -v

Get all employees:
curl -X GET http://localhost:5000/api/employees/all \
  -H "accessToken: 732935fe39094ac085d6a1b883965d7e"

2)Return specific employee
curl -X GET "http://localhost:5000/api/employees/1 \
     -H "accessToken: 732935fe39094ac085d6a1b883965d7e"

3)create a specific employee
curl -X POST "http://localhost:5000/api/employees" \
     -H "accessToken: 732935fe39094ac085d6a1b883965d7e" \
     -H "Content-Type: application/json" \
     -d '[{
           "firstname": "Yasmine",
           "lastname": "Mahfoudhi",
           "email": "yasmine.mahfoudhi@gmail.com"
         }]'

4)update specific employee
PATCH (Partial Update):
curl -X PATCH http://localhost:5000/api/employees/1 \
  -H "accessToken: 732935fe39094ac085d6a1b883965d7e" \
  -H "Content-Type: application/json" \
  -d '{
        "firstname": "Yasmine_Updated",
        "lastname": "Mahfoudhi_Updated",
        "email": "yasmine.updated@gmail.com",
        "id": 1
      }'


PUT (Full Update):
curl -X PUT http://localhost:5000/api/employees/1 \
  -H "accessToken: 732935fe39094ac085d6a1b883965d7e" \
  -H "Content-Type: application/json" \
  -d '{
        "firstname": "Yasmine_Updated",
        "lastname": "Mahfoudhi_Updated",
        "email": "yasmine.updated@gmail.com",
        "id": 1
      }'

5)
curl -X DELETE http://localhost:5000/api/employees/1 \
  -H "accessToken: 732935fe39094ac085d6a1b883965d7e" \
  -H "Content-Type: application/json" \
  -d '{
        "id": 1
      }'

6)
curl -X GET http://localhost:5000/api/employees/1 \
  -H "accessToken: 6b3d63fd145e4fc0bc4a177077b58199"
