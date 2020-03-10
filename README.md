# spring-restapi-with-security
Spring Boot RESTAPI Project with Spring Security

**Sign Up**

POST /api/signup

Request Body
```
{
        "username": "hoge",
        "email": "hoge@fuga.com",
        "password": "12345678",
        "role": ["mod", "user"]
}
```
to Sign Up. registered with each tables.

---

**Sign in***

POST /api/signin

Request Body

```
{
	
	"username": "hoge",
	"password": "12345678"
}

```
to get a token.

when access authorized page add request header.

```
Authorization: Bearer {$token}
```

---

**Test all***

GET /api/test/all

No Authorities required.

***Test user***

GET /api/test/user

User Role required.
token is valid and has user role then see the "User Content", otherwise thrown a exception.

***Test mod***

GET /api/test/mod

Moderate Role required
token is valid and has moderate role then see the "User Content", otherwise thrown a exception.

***Test admin***

GET /api/test/admin

Admin Role required.
token is valid and has admin role then see the "User Content", otherwise thrown a exception.

