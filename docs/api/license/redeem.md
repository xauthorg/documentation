---
sidebar_position: 4
title: "Redeem"
---

# Redeem License
The `/license/redeem/{license_key}` endpoint is used to retrieve the information of a specific license using the license key. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/license/redeem/{license_key}`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `Cookie`

## Path Parameters
`license_key`: The key of the license you want to delete.

## Response
This endpoint does not return any content in the response body, but HTTP status codes are used to indicate success or failure of the operation

## Note
The `/license/redeem/{license_key}` endpoint requires a valid Cookie from the user who wants to redeem the license. The license key needs to be included in the path of the request.
This endpoint requires you to specify a license key in the path to retrieve the corresponding license's information.