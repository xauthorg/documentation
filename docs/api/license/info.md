---
sidebar_position: 3
title: "Info"
---

# Get License Info
The `/license/info/{license_key}` endpoint is used to retrieve the information of a specific license using the license key. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/license/info/{license_key}`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
`license_key`: The key of the license you want to delete.

## Response
If the request is successful, the response will be a JSON object containing the license's information:

- `id`: The ID of the license.
- `license_key`: The license key.
- `created_by`: The name of the user who created the license.
- `used`: A boolean indicating whether the license has been used.
- `days`: The duration of the license in days.
- `plan`: The plan associated with the license.

## Note
This endpoint requires you to specify a license key in the path to retrieve the corresponding license's information.