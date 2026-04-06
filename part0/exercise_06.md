sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks Save button
    Note right of browser: JS code adds the note to the list and rerenders it locally

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note left of server: Server saves the note and sends success status
    server-->>browser: 201 Created (JSON message)
    deactivate server