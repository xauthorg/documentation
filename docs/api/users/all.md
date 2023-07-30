---
title: "Get All Users"
sidebar_position: 1
---

# Get All Users

The `/users` endpoint is used to retrieve all users in the database. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/users`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Response
The endpoint responds with a `200 OK` status code and a JSON array containing all the user objects.

Each user object contains the following fields:

- `id`: The unique identifier of the user.
- `username`: The username of the user.
- `hwid`: The hardware ID of the user. This field can be null.
- `role`: The role assigned to the user.
- `createdAt`: The date and time when the user account was created.
- `modifiedAt`: The date and time when the user account was last modified.
- `loginAttempts`: The number of login attempts made by the user.
- `banned`: Indicates whether the user is banned (1 for banned, 0 for not banned).
- `banned_reason`: The reason why the user was banned.
- `lastLoginAttempt`: The date and time of the last login attempt made by the user. This field can be null.

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.

Example:
```json
[
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
    },
    {
        "id": "uuid",
        "username": "someuser",
        "hwid": "HWID123456789",
        "role": "admin",
        "createdAt": "datestring",
        "modifiedAt": "datestring",
        "loginAttempts": 3,
        "banned": 0,
        "banned_reason": "",
        "lastLoginAttempt": "datestring"
    }
]
```

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.