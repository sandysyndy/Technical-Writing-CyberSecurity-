#  API Documentation Practice: OpenWeatherMap Endpoint Breakdown

As part of my API foundations phase, I analyzed the core anatomy of a real-world public API endpoint to practice mapping out resources, base URLs, and paths.

##  Analyzed Endpoint
`GET https://api.openweathermap.org/data/2.5/weather`

---

##  Component Breakdown

| Component | Value | Description |
| :--- | :--- | :--- |
| **Protocol** | `https://` | Secure Hypertext Transfer Protocol. |
| **Base URL (Host)** | `api.openweathermap.org` | The root address of the API server. |
| **Path (Endpoint)** | `/data/2.5/weather` | The specific location of the current weather data resource. |
| **Method** | `GET` | Used to retrieve data from the server without modifying it. |

---

##  Key Takeaway
Documenting an API requires translating these technical components into clear instructions so developers know exactly where to direct their requests to fetch the correct resource.
