# jwt

`jwt` provides a simple way to create and verify JSON Web Tokens (JWTs) in Go. This package is built on top of the [golang-jwt/jwt](https://github.com/golang-jwt/jwt).

## Installation

```bash
go get -u github.com/WebXense/jwt
```

## Create a JWT Token

```go
secret := "not secret"

claims := jwt.New(secret)
claims.Set("name", "John Doe")
claims.Set("admin", true)

token, err := claims.Token()
```

## Verify/Parse JWT Token

```go
claims, err := jwt.NewFromToken(token, secret)
if err != nil {
    panic(err)
}

name := claims.Get("name").(string)
admin := claims.Get("admin").(bool)
```
