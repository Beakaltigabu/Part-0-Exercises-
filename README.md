# Part-0-Exercises-
**Exercise 0.4: New Note Diagram**
sequenceDiagram
    participant browser
    participant server

browser->>server: POST https://fullstack-exampleapp.herokuapp.com/new_note
activate server
server-->>browser: 302 Found
deactivate server

note left of server: the server asks the browser to do a new HTTP GET request to the address defined in the header's location 
browser->>server: GET https://fullstack-exampleapp.herokuapp.com/notes
activate server
server-->>browser: HTML Document
deactivate server
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: main.css
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server-->browser: main.js
deactivate server
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{"content": "HTML is easy", "date":"2023-1-1"},...]
deactivate server


**Exercise 0.5:Single page app diagram**
sequenceDiagram
    participant browser
    participant server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
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
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

**Exercise 0.6:Single page app diagram**
sequenceDiagram
    participant browser
    participant server

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate server
server-->>browser: 201: note created
deactivate server
    
