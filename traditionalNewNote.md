# Sequence diagram of adding a new note

This diagram demonstrates the sequence of events for adding a new note through the form.

## Diagram of adding a new note

```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Server-->>Client: HTTP Status code: 302(Found)

    Note left of Client: The server requests a URL redirect to /notes

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Client: HTTP Status code: 200(OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Client: Returns the CSS file with HTTP Status code: 200(OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Client: Returns the JS file with HTTP Status code: 200(OK)

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Client: Returns the JSON file with HTTP Status code: 200(OK)

    Note over Client,Server: Data is sent as the body of the POST request. <br/>Server can access using 'req.body' from the 'req' object
    Note over Client,Server: Server creates a new note object and adds it to an array called 'notes'
    Note over Client,Server: SNew notes are not saved in a DB, <br/>new notes dissapear when server restarts

```

- Make sure the code block starts with:

```markdown
```mermaid
```

- GitHub automatically renders Mermaid diagrams inside Markdown files like `README.md`.
