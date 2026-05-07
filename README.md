# Mermaid Flowchart Example

This README demonstrates the secuence of events for the example app requesting the picture and how the client communicates with the server.

## Diagram

```mermaid
sequenceDiagram
    Participant Browser
    Participant Server

    Browser->>+Server: HTTP GET https://fulstack-exampleapp.herokuapp.com 
    Server->>-Browser: HTML-code
    
    Browser->>+Server: HTTP GET https://fulstack-exampleapp.herojuapp.com/kuva.png
    Server-->>-Browser: image

    Note left of Browser: Browser displays a page\nwith image embedded
```

- Make sure the code block starts with:

```markdown
```mermaid
```

- GitHub automatically renders Mermaid diagrams inside Markdown files like `README.md`.
