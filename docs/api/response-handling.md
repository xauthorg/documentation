---
sidebar_position: 1
---
# Response Handling

All responses from our server are encrypted for security purposes. This means you will need to follow a specific process to decrypt and interpret the responses you receive. This section provides a step-by-step guide on how to handle, decrypt, and interpret server responses.

### Retrieve the Response
After making a request to the server, you'll receive a response in the following format:

```json
{
    "data": "<Base64-encoded ciphertext>"
}
```

The `data` field contains a Base64-encoded ciphertext.

### Base64 Decoding

First, you need to decode the ciphertext from Base64. Most programming languages have built-in functions or libraries for Base64 decoding. For example, in Python, you can use the `base64` module's `b64decode` function.

```py
import base64
decoded_ciphertext = base64.b64decode(ciphertext)
```

After this step, `decoded_ciphertext` will contain the raw bytes of the ciphertext.

### Decrypt the Ciphertext
After decoding, you need to decrypt the ciphertext using the appropriate key and decryption algorithm. The specifics of this step depend on the encryption method used by the server. In our case, we use AES-256.

```py
decrypted_data = decrypt(decoded_ciphertext, key)
```

Make sure to replace `decrypt` with the appropriate decryption function and `key` with the session cookie `_xauth_decryption_v1`.

### Interpret the Decrypted Data
```json
{
    "id": "<string>",
    "username": "<string>",
    "role": "<string>",
    "createdAt": "<string>",
    "modifiedAt": "<string>",
    "loginAttempts": <int>,
    "banned": <int>,
    "hwid": "<string>",  // optional
    "lastLoginAttempt": "<string>"  // optional
}
```

You can now interpret this data according to your application's requirements.

Remember that if you encounter any issues or need further assistance, please reach out to our support team at [discord.gg/xauth](https://discord.gg/xauth).

