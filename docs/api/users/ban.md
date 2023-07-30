---
title: "Toggle User Ban"
sidebar_position: 5
---
# Toggle User Ban
The `/users/{user_id}/toggle-ban` endpoint is used to toggle the ban status of a user. This endpoint uses a `POST` request.

URL: `<ID>.xauth.ru/users/{id}/toggle-ban`<br/>
Method: `POST`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
- `id`: The unique identifier of the user.

# Response
If the operation is successful, the endpoint responds with a `200 OK` status code and no body.

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue.