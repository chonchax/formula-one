# Formula One

## Requirements

- Docker Desktop installed
- Git

## Installation & Launch

```bash
git clone --recurse-submodules git@github.com:chonchax/formula-one.git
cd formula-one
docker compose up --build
```

Frontend: http://localhost:5174

Backend exposed at: http://localhost:3001/api/v1

## Frontend login:

```bash
Email: yann@test.com
Password: 123456
```

The VITE_API_URL variable is already configured to point to http://localhost:3001/api/v1.

## API - Authentication

POST /sign_in

Request JSON:

```bash
{
"user": {
"email": "yann@test.com",
"password": "123456"
}
}
```

Response:

```bash
{
"token": "<JWT_TOKEN>",
"user": {
"id": "27e9eb01-7f39-46d5-a476-1af7b174d71c",
"email": "yann@test.com",
"created_at": "2025-11-29T11:10:17.857Z"
}
}
```

## Use the token in the headers for protected routes:

```bash
Authorization: Bearer <JWT_TOKEN>
```
