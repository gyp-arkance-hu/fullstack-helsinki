# Task 0.4 – New Note (Traditional Web App)

When the user submits the note form on the traditional Notes page, the browser sends a POST request. The server responds with a redirect, causing the browser to reload the entire page.

```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Note over Browser: User types a note and clicks "Save"

    Browser->>Server: HTTP POST /new_note (form data: note content)
    Server-->>Browser: HTTP 302 Redirect → /notes

    Browser->>Server: HTTP GET /notes
    Server-->>Browser: HTML (notes page)

    Browser->>Server: HTTP GET /main.css
    Server-->>Browser: main.css

    Browser->>Server: HTTP GET /main.js
    Server-->>Browser: main.js

    Browser->>Server: HTTP GET /data.json
    Server-->>Browser: JSON (all notes)

    Note over Browser: JavaScript renders the notes list via DOM API
```
