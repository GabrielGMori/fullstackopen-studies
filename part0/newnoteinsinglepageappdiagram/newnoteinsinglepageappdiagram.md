```mermaid
sequenceDiagram;
  participant  bw  as  browser;
  participant  sv  as  server;

  Note  right  of  bw: The browser executes a callback function that adds a new note to the array of notes;
  Note  right  of  bw: The browser executes the function that renders the notes;
  Note  right  of  bw: The browser executes the function that sends the new note to the server;

  bw->>sv: POST  https://studies.cs.helsinki.fi/exampleapp/new_note_spa;
  activate  sv;
  note  left  of  sv: The server adds the new note to the array of notes;
  sv-->>bw: [{ "message": "note created"}];
  deactivate  sv;
```
