# PDF2TXT4NLP

Project Design
==============

The goal of this project is to build an online Python web app that accepts academic articles in PDF format and converts them into plain text. The app should be hosted on Heroku and should comply with OOP and ISO/IEC 25000:2005.

User Requirements
-----------------

The app should allow users to:

*   Access the app homepage and upload PDF files
*   View the progress of the conversion process
*   Download the resulting text files

The app should also be able to:

*   Validate the PDF files to ensure that they are valid and meet the app's requirements
*   Convert the PDF files to text using the PDFBoT library
*   Save the text files to the server

Sequence Diagram
----------------

The following sequence diagram illustrates how the app works:

```PlantUML
@startuml

actor User

User -> App: Access app homepage
App -> App: Display homepage template

User -> App: Upload PDFs
App -> App: Validate PDF files
App -> App: Save PDFs to server
App -> App: Create PDFConverter object
App -> App: Display progress bar
loop
  App -> PDFConverter: Convert PDF to text
  App -> App: Save text to server
  App -> App: Update progress bar
end
App -> App: Delete PDFConverter object
App -> App: Display success message

User -> App: Download texts
App -> App: Serve text files to user

@enduml
```

This sequence diagram shows the basic flow of how the app works. When the user accesses the app's homepage, the app displays the homepage template. The user can then upload PDF files, which the app validates and saves to the server. The app then uses the `PDFConverter` object to convert the PDFs to text and displays a progress bar to the user. As each PDF is converted and saved, the progress bar is updated. When the conversion process is complete, the `PDFConverter` object is deleted and the user is shown a success message. Finally, the user can download the resulting text files from the app.
