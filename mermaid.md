squenceDiagram
  participant browser
  participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note (note content)
    activate server
    server-->>browser: Redirect to /notes
    deactivate server

    browser->>server: GET /notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET /main.js
    activate server
    server-->>browser: JavaScript file
    deactivate server

    Note right of browser: Browser executes JS to fetch notes data

    browser->>server: GET /data.json
    activate server
    server-->>browser: Updated notes JSON (including new note)
    deactivate server

    Note right of browser: Browser renders the updated notes list
```
