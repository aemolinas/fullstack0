## New Note Submission Sequence Diagram
*Submitting a New Note*
```mermaid
sequenceDiagram
    actor User
    participant Browser
    participant Server
    User->>+Browser: Submit button
    Browser->>+Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Browser->>+Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>-Browser: HTML file
    Browser->>+Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>-Browser: CSS file 
    Browser->>+Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>-Browser: JS file
    Browser-->>-Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>-Browser: data.json
    Browser->>+Server: GET https://studies.cs.helsinki.fi/favicon.ico
    Server-->>-Browser: favicon.ico 
```
##