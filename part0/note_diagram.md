# form

<div class="mermaid">
sequenceDiagram
participant browser
participant server

browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
server -->>browser: HTTP 302
Note right of server: The server rquests to browser to make a new HTTP GET request
deactivate server


browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
activate server
server -->> browser: HTML-code[notes]
deactivate server
 

browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server -->> browser: CSS-code[main.css]
deactivate server


browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server -->> browser: JS-code[main.js]
Note left of browser: browser starts executing JS-code that requests JSON data from server
deactivate server

browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server -->> browser: JSON-file[data.json]
deactivate server

</div>