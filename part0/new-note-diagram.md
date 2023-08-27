sequenceDiagram
    participant browser
    participant server
    Note right of browser: The user fills the input note and click the save button of the form.
    browser-->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: Response with a Status code 302, URL Redirect.
    deactivate server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document with new notes
    deactivate server