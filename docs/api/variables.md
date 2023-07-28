---
sidebar_position: 3
---
# Variables

The `/variables` endpoint is used to fetch a specific variable by its ID. This endpoint uses a `GET` request, which must include the `id` of the variable in the request's query parameters.

URL: `<ID>.xauth.ru/variables?id=<VARIABLE_ID>`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
2. `Cookie` - Only required for protected variables

## Query Parameters
- `id`: The ID of the desired variable as a string.

Example:

`<ID>.xauth.ru/variables?id=<VARIABLE_ID>`

## Response (With Valid Cookie)
If the request is successful, the response will be a JSON object containing the value of the requested variable

For signed in users, the response will be encrypted and base64-encoded, and it will be a JSON object with a single property, `data`, which will contain the encrypted and encoded response data.

If the cookie is not valid, a 401 Unauthorized status code is returned with the message `Not authorized`.

Example (Signed in users):

```json
{
    "data": "<BASE64-ENCODED_ENCRYPTED_RESPONSE>"
}
```

## Response (No Cookie)
For not signed in users, the response will be a JSON object with a single property, `value`, which will contain the value of the requested variable.

Example (Not signed in users):
```json
{
    "value": "<VARIABLE_VALUE>"
}
```