sequenceDiagram
    participant browser
    participant server

    Note left of browser: event handler runs on<br/>submitting the form that<br/>creates a new note and<br/>adds it to the existing<br/>list of notes

    Note left of browser: browser then sends the<br/>new note to the server<br/>through POST request

    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa<br/>{ "content": "testingspa", "date": "2026-07-21T00:00:00.000Z" }

    Note right of server: server acknowledges creation<br/>of new resource and sends<br/>back an HTTP Status 201

    server-->>browser: 201 CREATED