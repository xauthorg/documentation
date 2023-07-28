---
sidebar_position: 2
title: "Delete"
---

# Delete License

The `/license/delete/{license_key}` endpoint is used to delete a specific license using the license key. This endpoint uses a `DELETE` request.

URL: `<ID>.xauth.ru/license/delete/{license_key}`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `XAuth-Moderate`

## Path Parameters
`license_key`: The key of the license you want to delete.

## Response
This endpoint does not return any content in the response body, but HTTP status codes are used to indicate success or failure of the operation

## Note
This endpoint requires you to specify a license key in the path to retrieve the corresponding license's information.