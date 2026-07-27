#  How REST APIs Talk: A Guide for Beginners

This guide breaks down the core mechanisms of RESTful APIs, HTTP communication protocols, status codes, and JSON structure for non-technical stakeholders and junior developers.

---

## 1. The HTTP Request Anatomy

Clients send HTTP requests to ask a server for data or actions. Every request contains key components:

* **HTTP Methods (Verbs):**
  * `GET`: The client fetches a resource (Read-only, non-destructive).
  * `POST`: The client creates a new resource on the server.
  * `PUT`: The client replaces or updates an existing resource entirely.
  * `DELETE`: The client permanently removes a resource from the server.
* **Headers:** The client attaches metadata to provide context (e.g., `Content-Type: application/json`, `Authorization: Bearer <token>`).

---

## 2. Server Response Status Codes

API servers respond with 3-digit status codes to signal the result of an operation:

| Code Range | Category | Common Examples |
| :--- | :--- | :--- |
| **2xx** | Success | `200 OK` (The server successfully processed the request), `201 Created` (The server successfully created the resource) |
| **4xx** | Client Error | `400 Bad Request` (The client sent malformed syntax), `401 Unauthorized` (The client omitted an authentication token) |
| **5xx** | Server Error | `500 Internal Server Error` (The server encountered an internal fault) |

---

## 3. Reading JSON Payloads

Systems exchange data using JavaScript Object Notation (JSON) organized in key-value pairs:

```json
{
  "user_id": 102,
  "status": "active",
  "roles": ["admin", "editor"]
}
