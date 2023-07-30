---
title: "Clear User Hardware ID"
sidebar_position: 4
---

# Clear User Hardware ID
The `/users/{id}/reset/hwid` endpoint is used to clear the hardware ID (hwid) of a user with a specific ID. This endpoint uses a `POST` request.

URL: `<ID>.xauth.ru/users/{id}/reset/hwid`<br/>
Method: `POST`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
- `id`: The unique identifier of the user.

## Response
If the operation is successful, the endpoint responds with a `200 OK` status code and a JSON object indicating success:

```json
{
    "success": true
}
```

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.