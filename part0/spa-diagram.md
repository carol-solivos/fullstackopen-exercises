sequenceDiagram
    participant browser
    participant server
    browser-->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document and JS
    deactivate server
    Note right of browser: The user fills the input note and click the save button of the form.
    browser-->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa 
    activate server
    server-->>browser: Response with a Status code 201 and adds the new note to de DOM.
    deactivate server
