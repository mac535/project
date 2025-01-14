```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant SPA
    participant Server
    participant Database

    %% Step 1: User creates a new note
    User->>Browser: Types a new note in the input field
    User->>Browser: Clicks the "Save" button
    Browser->>SPA: Sends new note data to SPA (POST /notes)
    SPA->>Server: Forwards new note data to the server
    Server->>Database: Saves the new note in the database
    Database-->>Server: Confirms note save
    Server-->>SPA: Sends success response (HTTP 200)
    SPA-->>Browser: Updates UI with the new note (dynamically)
    Browser-->>User: Displays the new note in the list
