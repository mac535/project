```mermaid
sequenceDiagram
    participant User
    participant WebPage
    participant Server
    participant Database

    User->>WebPage: Enters text into the text field
    User->>WebPage: Clicks the Save button
    WebPage->>Server: Sends note data (text) to server
    Server->>Database: Saves the new note to the database
    Database-->>Server: Confirmation of note saved
    Server-->>WebPage: Returns success response
    WebPage-->>User: Displays confirmation or new note
