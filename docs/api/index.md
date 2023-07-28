# API Endpoints

This section provides detailed documentation for each API route exposed by our API service. For each endpoint, you will find information about the HTTP method, URL structure, request parameters, and response format.


:::caution
Please note that some responses from the server are encrypted. To process the responses, you need to decrypt the Base64-encoded ciphertext using the appropriate key and decryption algorithm. Check our "Response Handling" section for more details on how to decrypt and interpret server responses.
:::


### Requesting Support
If you have any issues or questions related to our API, please reach out to our support team at [discord.gg/xauth](https://discord.gg/xauth). We're more than happy to assist!

## What is the Authorization header?

The Authorization header is a key component of HTTP protocol requests, especially when accessing secure resources. It is mandatory when interacting with our API. This header carries the credentials to authenticate a user agent with a server.

### What does it comprise?

The structure of an Authorization header is typically a string that follows the format `Bearer <HEADER> <SECRET>`.
