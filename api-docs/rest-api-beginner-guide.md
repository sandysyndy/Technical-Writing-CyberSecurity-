#  How REST APIs Talk: A Guide for Beginners

This guide breaks down the core mechanisms of RESTful APIs, HTTP communication protocols, status codes, and JSON structure for non-technical stakeholders and junior developers.

---

## 1. The HTTP Request Anatomy

An HTTP request acts as a request message sent from a client to a server. Every request contains key components:

* **HTTP Methods (Verbs):**
  * `GET`: Fetches a resource (Read-only, non-destructive).
  * `POST`: Creates a new resource.
  * `PUT`: Replaces/updates an existing resource entirely.
  * `DELETE`: Permanently removes a resource.
* **Headers:** Metadata providing context (e.g., `Content-Type: application/json`, `Authorization: Bearer <token>`).

---

## 2. Server Response Status Codes

API servers respond with 3-digit status codes to signal the result of an operation:

| Code Range | Category | Common Examples |
| :--- | :--- | :--- |
| **2xx** | Success | `200 OK` (Success), `201 Created` (Resource successfully built) |
| **4xx** | Client Error | `400 Bad Request` (Malformed syntax), `401 Unauthorized` (Missing token) |
| **5xx** | Server Error | `500 Internal Server Error` (Server fault) |

---

## 3. Reading JSON Payloads

Data is exchanged using JavaScript Object Notation (JSON) organized in key-value pairs:

```json
{
  "user_id": 102,
  "status": "active",
  "roles": ["admin", "editor"]
}
