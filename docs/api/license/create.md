---
sidebar_position: 2
title: "Create"
---

# Create Licenses

The `/license/create` endpoint is used to create a batch of licenses. This endpoint uses a `POST` request, which must include the license count, plan, duration (in days), and the creator's username in the request body.

URL: `<ID>.xauth.ru/license/create`<br/>
Method: `POST`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Request Body

A JSON object that includes:

- `count`: The number of licenses to be created as an integer. This must be greater than 0.
- `plan`: The plan name for the licenses as a string. This cannot be empty.
- `days`: The duration for which the licenses are valid in days as an integer. This must be greater than 0.
- `created_by`: The username or id of the user creating the licenses as a string. This cannot be empty.

Example:

```json
{
    "count": 10,
    "plan": "someplan",
    "days": 30,
    "created_by": "123"
}
```

## Response
If the request is successful, the response will be a 200 OK status, and the response body will contain a JSON array of the created licenses.