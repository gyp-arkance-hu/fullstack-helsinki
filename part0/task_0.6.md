# Task 0.6 – New Note (SPA Version)

In the SPA, submitting a new note does not trigger a traditional form submission. Instead, `spa.js` intercepts the event, sends the data as JSON via POST, and updates the DOM directly — no redirect, no page reload.

```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Note over Browser: User types a note and clicks "Save"
    Note over Browser: spa.js calls preventDefault()<br/>on the form submit event

    Browser->>Server: HTTP POST /new_note_spa<br/>Content-Type: application/json<br/>{"content": "...", "date": "..."}
    Server-->>Browser: HTTP 201 Created

    Note over Browser: spa.js appends the new note<br/>to the local list and updates the DOM<br/>(no page reload)
```
