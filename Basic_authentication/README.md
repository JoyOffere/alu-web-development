# Basic Authentication

Basic authentication is a simple authentication scheme built into the HTTP protocol. The client sends HTTP requests with the `Authorization` header that contains the word `Basic` followed by a space and a base64-encoded string `username:password`.

## How it works

1. The client sends a request to the server.
2. The server responds with a `401 Unauthorized` status and a `WWW-Authenticate` header.
3. The client sends another request with the `Authorization` header containing the base64-encoded credentials.
4. The server decodes the credentials and checks if they are valid.
5. If valid, the server responds with the requested resource; otherwise, it responds with `401 Unauthorized`.

## Example

Here is an example of a request with basic authentication:

```
GET /protected-resource HTTP/1.1
Host: example.com
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
```

In this example, `dXNlcm5hbWU6cGFzc3dvcmQ=` is the base64-encoded string for `username:password`.

## Security Considerations

- Basic authentication is not secure over plain HTTP as the credentials can be easily intercepted.
- Always use HTTPS to encrypt the credentials.
- Consider using more secure authentication methods like OAuth or token-based authentication.

## References

- [MDN Web Docs: HTTP Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
- [RFC 7617: The 'Basic' HTTP Authentication Scheme](https://tools.ietf.org/html/rfc7617)