# Auth API

Base path: `/v1/auth`

---

## POST /auth/register

Register a new user.

### Request Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password1"
}
```

| Field      | Type   | Required | Validation                              |
|------------|--------|----------|-----------------------------------------|
| `name`     | string | yes      | —                                       |
| `email`    | string | yes      | Valid email format                      |
| `password` | string | yes      | Min 8 chars, at least one letter + number |

### Responses

| Status | Description         | Body                        |
|--------|---------------------|-----------------------------|
| `201`  | Created             | `{ user, tokens }`          |
| `400`  | Email already taken | `{ code, message }`         |

---

## POST /auth/login

Login with email and password.

### Request Body

```json
{
  "email": "john@example.com",
  "password": "password1"
}
```

| Field      | Type   | Required |
|------------|--------|----------|
| `email`    | string | yes      |
| `password` | string | yes      |

### Responses

| Status | Description            | Body                |
|--------|------------------------|---------------------|
| `200`  | OK                     | `{ user, tokens }`  |
| `401`  | Invalid credentials    | `{ code, message }` |

---

## POST /auth/logout

Invalidate a refresh token.

### Request Body

```json
{
  "refreshToken": "<token>"
}
```

| Field          | Type   | Required |
|----------------|--------|----------|
| `refreshToken` | string | yes      |

### Responses

| Status | Description       |
|--------|-------------------|
| `204`  | No content        |
| `404`  | Token not found   |

---

## POST /auth/refresh-tokens

Get new access and refresh tokens using a valid refresh token.

### Request Body

```json
{
  "refreshToken": "<token>"
}
```

| Field          | Type   | Required |
|----------------|--------|----------|
| `refreshToken` | string | yes      |

### Responses

| Status | Description      | Body                  |
|--------|------------------|-----------------------|
| `200`  | OK               | `{ access, refresh }` |
| `401`  | Unauthorized     | `{ code, message }`   |

---

## POST /auth/forgot-password

Send a password reset email.

### Request Body

```json
{
  "email": "john@example.com"
}
```

| Field   | Type   | Required | Validation         |
|---------|--------|----------|--------------------|
| `email` | string | yes      | Valid email format |

### Responses

| Status | Description          |
|--------|----------------------|
| `204`  | Email sent           |
| `404`  | Email not registered |

---

## POST /auth/reset-password

Reset password using a reset token.

### Query Parameters

| Param   | Type   | Required | Description              |
|---------|--------|----------|--------------------------|
| `token` | string | yes      | Reset password JWT token |

### Request Body

```json
{
  "password": "newpassword1"
}
```

| Field      | Type   | Required | Validation                              |
|------------|--------|----------|-----------------------------------------|
| `password` | string | yes      | Min 8 chars, at least one letter + number |

### Responses

| Status | Description          | Body                |
|--------|----------------------|---------------------|
| `204`  | Password reset       | —                   |
| `401`  | Reset failed         | `{ code, message }` |

---

## POST /auth/send-verification-email

Send an email verification link. Requires authentication.

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Responses

| Status | Description   |
|--------|---------------|
| `204`  | Email sent    |
| `401`  | Unauthorized  |

---

## POST /auth/verify-email

Verify email address using a verification token.

### Query Parameters

| Param   | Type   | Required | Description               |
|---------|--------|----------|---------------------------|
| `token` | string | yes      | Email verification JWT token |

### Responses

| Status | Description          | Body                |
|--------|----------------------|---------------------|
| `204`  | Email verified       | —                   |
| `401`  | Verification failed  | `{ code, message }` |

---

## POST /auth/google-login

Login or register using a Google OAuth token.

### Responses

| Status | Description      | Body               |
|--------|------------------|--------------------|
| `200`  | OK               | `{ user, tokens }` |
| `401`  | Unauthorized     | `{ code, message }`|
