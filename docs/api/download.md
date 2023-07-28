---
sidebar_position: 4
---
# Download

The `/download` endpoint is used to download a specific file by its ID. This endpoint uses a `GET` request, which must include the `id` of the file in the request's query parameters. Note that a user must be signed in to use this endpoint.

URL: `<ID>.xauth.ru/download?id=<FILE_ID>`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
2. `Cookie`

## Query Parameters
- `id`: The ID of the desired file as a string.

Example:

`<ID>.xauth.ru/download?id=<FILE_ID>`

# Response
If the request is successful, the response will be the requested file's content, which is encrypted. The encrypted file will be sent as a binary stream in the HTTP response body, and the response headers will instruct the client to download the file, with the file name set to `_xauth_enc_<ORIGINAL_FILE_NAME>`.

If the cookie is not valid, a 401 Unauthorized status code is returned with the message `Not authorized`.