#  User Management API Reference Manual

This reference manual documents the resources, query parameters, request bodies, and error resolution paths for the User Management microservice.

---

## 1. Resource Overview & Base Path

The User Management API enables administrators to query, provision, and update system user records.

* **Base URL:** `https://api.enterprise.com/v1`
* **Authentication:** Bearer Token required in request header (`Authorization: Bearer <token>`).

---

## 2. Endpoint Specification: Fetch Users

`GET /users`

Retrieves a paginated list of user objects filtered by status or role.

### Query Parameters

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `status` | String | Optional | Filters results by account state (`active`, `suspended`). Default: `active`. |
| `limit` | Integer | Optional | Controls page size (Min: `1`, Max: `100`). Default: `20`. |
| `page` | Integer | Optional | Specifies the target page index. Default: `1`. |

---

## 3. Endpoint Specification: Create User

`POST /users`

Provisions a new user profile in the system.

### Request Body (`application/json`)

{
  "email": "user@enterprise.com",
  "role": "editor",
  "department_id": 402
}

### Property Schema

* `email` (String, Required): Valid corporate email address.
* `role` (String, Required): System access role (`admin`, `editor`, `viewer`).
* `department_id` (Integer, Required): Numeric identifier for departmental assignment.

### Response Example (`201 Created`)

{
  "id": 1089,
  "email": "user@enterprise.com",
  "role": "editor",
  "department_id": 402,
  "created_at": "2026-08-20T14:30:00Z"
}

---

## 4. Error Resolution Catalog

When an API request fails, the server returns a structured error object. Use this catalog to resolve non-200 states.

### `400 Bad Request`

* **Cause:** The client payload contains malformed JSON, invalid data types, or missing required fields.
* **Sample Error Payload:**

{
  "code": "INVALID_PARAMETER",
  "message": "The field 'email' must contain a valid email address."
}

* **Remediation Steps:**
  1. Validate the request body syntax using a JSON linter.
  2. Confirm all required fields (`email`, `role`, `department_id`) exist in the payload.
  3. Verify data types match schema constraints (e.g., ensure `department_id` is an integer).

### `401 Unauthorized`

* **Cause:** The request lacks a valid authentication token or the token has expired.
* **Sample Error Payload:**

{
  "code": "TOKEN_EXPIRED",
  "message": "Bearer token has expired."
}

* **Remediation Steps:**
  1. Inspect the `Authorization` request header.
  2. Confirm the token follows the format `Bearer <token_string>`.
  3. Request a fresh authentication token from the `/auth/login` endpoint.
