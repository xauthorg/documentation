---
sidebar_position: 6
title: "Get All Unused"
---

# Get All Unused Licenses
The `/license/unused` endpoint is used to retrieve all unused licenses. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/license/unused`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`


## Response
If the request is successful, the response will be a 200 OK status, and the response body will contain a JSON array of all unused licenses.

Each license object in the array includes:

- `id`: The unique identifier of the license as an integer.
- `license_key`: The license key as a string.
- `created_by`: The username of the user who created the license as a string.
- `used`: A boolean value indicating whether the license has been used. For this endpoint, this will always be false.
- `days`: The duration for which the license is valid in days as an integer.
- `plan`: The plan associated with the license as a string.

Example:

```json
[
    {
        "id": 1,
        "license_key": "uuid",
        "created_by": "123",
        "used": false,
        "days": 30,
        "plan": "someplan"
    },
    {
        "id": 2,
        "license_key": "uuid",
        "created_by": "123",
        "used": false,
        "days": 30,
        "plan": "someplan"
    }
]
```

### If there are no unused licenses then the response will be `null`