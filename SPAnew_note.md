## New Note Submission Sequence Diagram
*Submitting a New Note in the Single Page App*
```mermaid
sequenceDiagram
    actor User
    participant Browser
    participant Server
    User->>+Browser: Submit button
    Browser->>+Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
```
##