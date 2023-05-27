## New Note Submission Sequence Diagram
*Submitting a New Note*
```mermaid
sequenceDiagram
    actor User
    participant browser
    participant server

    User->>browser: Submit button
    
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note

    Note right of browser: The POST request to "new_note" returns HTTP code 302, a redirect to "notes."

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML file
    deactivate server
    
    Note right of browser: Browser parses the head of "notes" and requests main.css and main.js

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server 
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JS file
    deactivate server

    Note right of browser: The browser executes JavaScript that fetches the JSON file from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: data.json
    deactivate server

    Note right of browser: A call back function renders the notes page using the DOM-API with the JSON data
    
    browser->>server: GET https://studies.cs.helsinki.fi/favicon.ico
    activate server
    server-->>browser: favicon.ico
    deactivate server
```
##