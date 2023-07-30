---
title: "Get User By ID"
sidebar_position: 3
---
# Get User By ID
The `/users/{id}` endpoint is used to retrieve details of a user with a specific ID. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/users/{id}`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
- `id`: The unique identifier of the user.

## Response
The endpoint responds with a `200 OK` status code and a JSON object containing the user details:

Example:
```json
{
    "id": "uuid",
    "username": "someuser",
    "hwid": null,
    "role": "user",
    "createdAt": "datestring",
    "modifiedAt": "datestring",
    "loginAttempts": 0,
    "banned": 0,
    "banned_reason": "",
    "lastLoginAttempt": null
}
```

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.