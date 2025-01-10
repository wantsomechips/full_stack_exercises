
## Part 0: Exercises 0.1.-0.6

### Exercise 0.1

No submission needed.

### Exercise 0.2

No submission needed.

### Exercise 0.3

No submission needed.

###  Exercise 0.4 

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User type in the text field and clcik the Save button.

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Note right of browser: The new note is sent along with the request.

    activate server
    Note left of server: Create a new note and update the notes array.

    server-->>browser: URL Redirection Request
    deactivate server

    Note right of browser: Browser reload the page.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes

    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "test 2", "date": "2025-1-10" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes.

    
```

###  Exercise 0.5 

```mermaid
sequenceDiagram
    participant browser
    participant server


    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa 
    
    activate server
    server-->>browser: HTML document
    deactivate server


    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    
    activate server
    server-->>browser: the CSS file
    deactivate server


    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    
    activate server
    server-->>browser: the JS file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.js
    
    activate server
    server-->>browser: [{content: "", date: "2025-01-10T08:05:06.792Z"},…]
    deactivate server
    
    Note right of browser: The browser executes the callback function that renders the notes.

```

###  Exercise 0.6 
```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User type in the text field and clcik the Save button.

    Note right of browser: JS code in browser re-draw the notes and sent the new note to server.

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa <br> {content: "test3", date: "2025-01-10T14:56:33.440Z"}

    activate server
    Note left of server: Create new note.

    server-->>browser: {"message":"note created"}
    deactivate server
    
```