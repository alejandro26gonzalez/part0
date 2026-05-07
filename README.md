# Mermaid Flowchart Example

This README demonstrates the secuence of events for adding a new note thorugh the form.

## Diagram of adding a new note

```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Server-->>Client: HTTP Status code: 302 (Found)

    Note left of Browser: URL redirection request from the server to the location 'notes'

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Client: HTTP Status code: 200 (OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Client: Returns the CSS file along HTTP Status code: 200 (OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Client: Returns the JS file along HTTP Status code: 200 (OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Server->>Client: Returns the JSON file along HTTP Status code: 200(OK)

```

- Make sure the code block starts with:

```markdown
```mermaid
```

- GitHub automatically renders Mermaid diagrams inside Markdown files like `README.md`.
