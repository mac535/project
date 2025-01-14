```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant SPA
    participant Server
    participant Database

    %% Step 1: User visits the SPA
    User->>Browser: Opens the URL https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>SPA: Loads the SPA JavaScript & CSS
    SPA->>Server: Sends GET request to fetch existing notes (GET /notes)
    Server->>Database: Fetches the list of notes
    Database-->>Server: Returns notes data
    Server-->>SPA: Sends the notes to SPA
    SPA-->>Browser: Renders the notes on the page
    Browser-->>User: Displays the list of notes

    %% Step 2: User interacts with the SPA
    User->>Browser: Types a new note in the input field
    User->>Browser: Clicks the "Save" button
    Browser->>SPA: Sends new note data (POST /notes)
    SPA->>Server: Forwards note data to the server
    Server->>Database: Saves the new note
    Database-->>Server: Confirms note save
    Server-->>SPA: Sends success response
    SPA-->>Browser: Updates the UI with the new note
    Browser-->>User: Displays the new note
