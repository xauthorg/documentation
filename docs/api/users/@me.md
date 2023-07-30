---
title: "Get Current User"
sidebar_position: 2
---

# Get Current User

The `/users/@me` endpoint is used to retrieve details of the current authenticated user. This endpoint uses a `GET` request.


URL: `<ID>.xauth.ru/users/@me`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `Cookie`

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