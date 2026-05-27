# Users API

Base path: `/v1/users`

All endpoints require a valid Bearer token. Admin role is required for most operations.

---

## POST /users

Create a new user. Requires `manageUsers` permission (admin only).

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Request Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password1",
  "role": "user"
}
```

| Field      | Type   | Required | Validation                                |
|------------|--------|----------|-------------------------------------------|
| `name`     | string | yes      | —                                         |
| `email`    | string | yes      | Valid email, must be unique               |
| `password` | string | yes      | Min 8 chars, at least one letter + number |
| `role`     | string | yes      | Enum: `user`, `admin`                     |

### Responses

| Status | Description         | Body                |
|--------|---------------------|---------------------|
| `201`  | Created             | `User` object       |
| `400`  | Email already taken | `{ code, message }` |
| `401`  | Unauthorized        | `{ code, message }` |
| `403`  | Forbidden           | `{ code, message }` |

---

## GET /users

Get a paginated list of all users. Requires `getUsers` permission (admin only).

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Query Parameters

| Param    | Type    | Required | Default | Description                              |
|----------|---------|----------|---------|------------------------------------------|
| `name`   | string  | no       | —       | Filter by name                           |
| `role`   | string  | no       | —       | Filter by role (`user` or `admin`)       |
| `sortBy` | string  | no       | —       | Sort field and order, e.g. `name:asc`    |
| `limit`  | integer | no       | `10`    | Max results per page (min: 1)            |
| `page`   | integer | no       | `1`     | Page number (min: 1)                     |

### Responses

| Status | Description  | Body                                                    |
|--------|--------------|---------------------------------------------------------|
| `200`  | OK           | `{ results, page, limit, totalPages, totalResults }`    |
| `401`  | Unauthorized | `{ code, message }`                                     |
| `403`  | Forbidden    | `{ code, message }`                                     |

---

## GET /users/:userId

Get a single user by ID. Logged-in users can only fetch their own data; admins can fetch any user.

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Path Parameters

| Param    | Type     | Required | Description      |
|----------|----------|----------|------------------|
| `userId` | ObjectId | yes      | MongoDB user ID  |

### Responses

| Status | Description  | Body                |
|--------|--------------|---------------------|
| `200`  | OK           | `User` object       |
| `401`  | Unauthorized | `{ code, message }` |
| `403`  | Forbidden    | `{ code, message }` |
| `404`  | Not found    | `{ code, message }` |

---

## PATCH /users/:userId

Update a user. Logged-in users can only update themselves; admins can update any user.

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Path Parameters

| Param    | Type     | Required | Description     |
|----------|----------|----------|-----------------|
| `userId` | ObjectId | yes      | MongoDB user ID |

### Request Body

At least one field is required.

```json
{
  "name": "New Name",
  "email": "newemail@example.com",
  "password": "newpassword1"
}
```

| Field      | Type   | Required | Validation                                |
|------------|--------|----------|-------------------------------------------|
| `name`     | string | no       | —                                         |
| `email`    | string | no       | Valid email, must be unique               |
| `password` | string | no       | Min 8 chars, at least one letter + number |

### Responses

| Status | Description         | Body                |
|--------|---------------------|---------------------|
| `200`  | OK                  | Updated `User` object |
| `400`  | Email already taken | `{ code, message }` |
| `401`  | Unauthorized        | `{ code, message }` |
| `403`  | Forbidden           | `{ code, message }` |
| `404`  | Not found           | `{ code, message }` |

---

## DELETE /users/:userId

Delete a user. Logged-in users can only delete themselves; admins can delete any user.

### Headers

| Header          | Value                  |
|-----------------|------------------------|
| `Authorization` | `Bearer <accessToken>` |

### Path Parameters

| Param    | Type     | Required | Description     |
|----------|----------|----------|-----------------|
| `userId` | ObjectId | yes      | MongoDB user ID |

### Responses

| Status | Description  | Body                |
|--------|--------------|---------------------|
| `204`  | No content   | —                   |
| `401`  | Unauthorized | `{ code, message }` |
| `403`  | Forbidden    | `{ code, message }` |
| `404`  | Not found    | `{ code, message }` |
