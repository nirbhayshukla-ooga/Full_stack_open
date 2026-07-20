sequenceDiagram
    participant browser
    participant server

    Note left of browser: browser sends new note<br/>form data through POST<br/>request to the server

    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    server-->>browser: 302 REDIRECT https://studies.cs.helsinki.fi/exampleapp/notes

    Note left of browser: browser is redirected to<br/>the /exampleapp/notes<br/>endpoint by the server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->>browser: HTML-code

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: main.css

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server-->>browser: main.js

    Note left of browser: browser executes javascript code<br/>that requests JSON notes data from server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: [{ content: "testing", date: "2021-08-19" }, ...]

    Note left of browser: browser executes event handler<br/>that renders the received notes
