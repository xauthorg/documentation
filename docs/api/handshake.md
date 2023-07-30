---
sidebar_position: 5
---
# Handshake
The `/handshake` endpoint allows for a secure communication between the client and the server. It uses a GET request.

URL: `<ID>.xauth.ru/handshake`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
2. `Cookie`

The client sends a request to this endpoint after the client and the server have both authenticated their identities. The server checks the JWT token in the client's cookie and retrieves the user's details. It then encrypts these details using a derived key based on the cookie's value.

## Response
If the operation is successful, the endpoint responds with a `200 OK` status code and a JSON object in the body that includes the user's encrypted data.

- `data`: A base64 string of the user's encrypted data.

Example:
```json
{
    "data": "<BASE64-ENCODED_ENCRYPTED_RESPONSE>"
}
```

If the request is unsuccessful, an appropriate HTTP status code will be returned with an error message describing the issue. For example, if the JWT token is invalid, a `401 Unauthorized` status code is returned with the message `Invalid token`.
