---
sidebar_position: 2
---
# Login

The `/login` endpoint is used to authenticate a user. This endpoint uses a `POST` request, which must include the user's `username`, `password`, and `hwid` (Hardware ID) in the request body.

URL: `<ID>.xauth.ru/login`<br/>
Method: `POST`<br/>
## Headers: 
1. `Content-Type: application/json`
2. `Authorization`

## Request Body

A JSON object that includes:

- `username`: The user's username as a string.
- `password`: The user's password as a string.
- `hwid`: The user's hardware ID as a string.

Example:

```json
{
    "username": "username",
    "password": "password",
    "hwid": "HWID"
}
```


## Response

If the request is successful, the response will be a 200 OK status with a message `Login successful`.

A session cookie will also be set, with the session ID being used for authentication on subsequent requests. The cookie is named according to the version of XAuth (Current: `_xauth_session_v1`), expires after 24 hours, and is sent with every HTTP request for 1 hour.

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.
