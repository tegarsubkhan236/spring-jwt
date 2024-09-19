# JWT Authentication with Spring Boot 3

This project demonstrates how to implement **JWT (JSON Web Token)** authentication in a **Spring Boot 3** application.

## Guide Reference
[JWT Authentication with Spring Boot 3](https://medium.com/@tericcabrel/implement-jwt-authentication-in-a-spring-boot-3-application-5839e4fd8fac)

## API Reference

#### Sign Up
```bash
  curl -v POST localhost:8080/auth/signup -H 'Content-Type:application/json' -d '{"email": "admin@email.com", "password": "qwerty", "fullName": "admin"}'
```
```json
{
    "id": 1,
    "fullName": "admin",
    "email": "admin@email.com",
    "password": "$2a$10$fcZhzBGSh1be2ZGnbfoIleYL6Dtehl9UfgZ9kpSCyASVJQ5f9WS.m",
    "enabled": true,
    "authorities": [],
    "username": "admin@email.com",
    "accountNonExpired": true,
    "accountNonLocked": true,
    "credentialsNonExpired": true
}
```

#### Login
```bash
  curl -v POST localhost:8080/auth/login -H 'Content-Type:application/json' -d '{"email": "admin@email.com", "password": "qwerty"}'
```
```json
{
    "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbkBlbWFpbC5jb20iLCJpYXQiOjE3MjY3MzIzMjYsImV4cCI6MTcyNjczNTkyNn0.Y7L9GdQAonkz4CViwKROdjDB9bZc7dVjsb28LjKci2I",
    "expiresIn": 3600000
}
```

#### Me
```bash
  curl -v localhost:8080/users/me
```
```json
{
  "id": 2,
  "fullName": "admin",
  "email": "admin@email.com",
  "password": "$2a$10$fcZhzBGSh1be2ZGnbfoIleYL6Dtehl9UfgZ9kpSCyASVJQ5f9WS.m",
  "enabled": true,
  "accountNonLocked": true,
  "authorities": [],
  "username": "admin@email.com",
  "accountNonExpired": true,
  "credentialsNonExpired": true
}
```

#### Users
```bash
  curl -v localhost:8080/users
```
```json
[
    {
        "id": 1,
        "fullName": "admin",
        "email": "admin@email.com",
        "password": "$2a$10$fcZhzBGSh1be2ZGnbfoIleYL6Dtehl9UfgZ9kpSCyASVJQ5f9WS.m",
        "enabled": true,
        "accountNonLocked": true,
        "authorities": [],
        "username": "admin@email.com",
        "accountNonExpired": true,
        "credentialsNonExpired": true
    }
]
```
