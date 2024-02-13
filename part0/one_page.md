# one page application diagram

A SPA is a different style of web app creation. We find that the form element of the HTML code doesn't have action or method atributtes and a place to send the input data.

```mermaid
sequenceDiagram
participant browser
participant server

browser ->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate server
server -->>browser: HTTP 201[{content: "content of the form", date: "actual_date"}]
Note right of server: The server doesn't request another a redirection, browser remains in the same page and doesn't send more HTTP requests.
```