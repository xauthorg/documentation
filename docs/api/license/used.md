---
sidebar_position: 4
title: "Used"
---

# Check if License is Used
The `/license/used/{license_key}` endpoint is used to check if a given license key has been used. This endpoint uses a `GET` request.

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
`license_key`: The key of the license you want to delete.

## Response
The endpoint responds with a 200 OK status code and a JSON object containing the `used` field, which will be `true` if the license has been used and `false` otherwise.

```json
{
    "used": true
}
```