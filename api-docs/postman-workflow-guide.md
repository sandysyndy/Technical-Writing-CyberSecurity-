#  Postman API Testing & Documentation Workflow Guide

This guide outlines the standard operational procedure for executing, organizing, and capturing API request workflows inside Postman for technical documentation.

---

## 1. Executing Requests & Interrogating Headers

The technical writer must verify live endpoint behavior before publishing documentation.

1. **Select the HTTP Method:** The writer sets the HTTP method verb (`GET`, `POST`, `PUT`, `DELETE`).
2. **Input the Request URL:** The writer enters the full URL containing the host and target path.
3. **Inspect Response Headers:** The client displays response metadata upon execution. The writer verifies key headers:
   * `Content-Type`: Confirms the data format (e.g., `application/json`).
   * `Cache-Control`: Defines caching rules for client requests.
   * `Date` & `Server`: Identifies host environment details.

---

## 2. Constructing POST Payloads

When documenting write-operations, the writer builds raw JSON body payloads to verify server processing:

```json
{
  "title": "API Documentation Workflow",
  "category": "Technical Writing",
  "is_published": true
}
