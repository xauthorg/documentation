---
sidebar_position: 3
---
# Register

The `/register` endpoint is used to register a new user. This endpoint uses a `POST` request, which must include the desired `username` and `password` in the request body.

URL: `<ID>.xauth.ru/register`<br/>
Method: `POST`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`

## Request Body
A JSON object that includes:

- `username`: The user's username as a string.
- `password`: The user's password as a string.

Example:

```json
{
    "username": "username",
    "password": "password",
}
```

## Response

If the request is successful, the response will be a 201 Created status with a message `User registered successfully`.
