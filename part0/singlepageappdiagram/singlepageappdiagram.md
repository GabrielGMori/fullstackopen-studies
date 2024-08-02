```mermaid
sequenceDiagram;
  participant bw as browser;
  participant sv as server;

  bw->>sv: GET https://studies.cs.helsinki.fi/exampleapp/spa;
  activate sv;
  sv-->>bw: HTML Document;
  deactivate sv;

  bw->>sv: GET https://studies.cs.helsinki.fi/exampleapp/main.css;
  activate sv;
  sv-->>bw: CSS File;
  deactivate sv;

  bw->>sv: GET https://studies.cs.helsinki.fi/exampleapp/spa.js;
  activate sv;
  sv-->>bw: JavaScript File;
  deactivate sv;
  Note right of bw: The browser starts executing the JavaScript code that fetches the JSON from the server;

  bw->>sv: GET https://studies.cs.helsinki.fi/exampleapp/data.json;
  activate sv;
  sv-->>bw: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ];
  deactivate sv;
  Note right of bw: The browser executes the callback function that renders the notes;
```
