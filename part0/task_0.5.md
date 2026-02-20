# Task 0.5 – Loading the SPA Notes Page

When the user navigates to the Single Page App version of the notes page, the browser fetches the base HTML, a stylesheet, the SPA JavaScript file, and the note data — then renders everything client-side without any further reloads.

```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: HTTP GET /spa
    Server-->>Browser: HTML (base SPA structure)

    Browser->>Server: HTTP GET /main.css
    Server-->>Browser: main.css

    Browser->>Server: HTTP GET /spa.js
    Server-->>Browser: spa.js (SPA logic)

    Browser->>Server: HTTP GET /data.json
    Server-->>Browser: JSON (all notes)

    Note over Browser: spa.js processes the JSON data<br/>and renders the notes list via DOM API<br/>(no page reload required)
```
