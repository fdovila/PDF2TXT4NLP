# PDF2TXT4NLP

TOC
===
# [Project Design][TOC1]
# [User Requirements][TOC2]
Sequence Diagram
OOP and ISO/IEC 25000:2005
Optimizing for Heroku
Deployment on Heroku
Ongoing Maintenance and Support
Conclusion

[Project Design](#TOC1)
==============

The goal of this project is to build an online Python web app that accepts academic articles in PDF format and converts them into plain text. The app should be hosted on Heroku and should comply with OOP and ISO/IEC 25000:2005.

[User Requirements](#TOC2)
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

OOP and ISO/IEC 25000:2005
--------------------------

This project follows OOP principles and the ISO/IEC 25000:2005 standard for software quality in several ways.

### OOP

*   The app's domain models, including the `PDFConverter` class, are organized into separate modules and are decoupled from the web app's controllers and routes. This follows the principle of separation of concerns, which helps to make the code more maintainable and easier to understand.
*   The `PDFConverter` object is created and deleted within the scope of the file conversion process. This follows the principle of object-oriented programming that objects should be created and destroyed as needed, rather than being persistently stored in memory.

### ISO/IEC 25000:2005

*   The app is organized into logical components, with clear separation of concerns between the different layers of the app. This follows the ISO/IEC 25000:2005 standard by providing a modular and scalable design that is easy to maintain and modify.
*   The app includes error handling to catch any exceptions that may occur during the conversion process. If an error occurs, the app can display an error message to the user and terminate the conversion process. This follows the ISO/IEC 25000:2005 standard by providing a robust and reliable user experience.

By following OOP principles and the ISO/IEC 25000:2005 standard, this project aims to deliver a high-quality and scalable web app that meets the user's needs.

Optimizing for Heroku
---------------------

To optimize the app for Heroku, the following strategies should be employed:

*   A lightweight web framework, such as Flask or Bottle, should be used to reduce the app's resource usage.
*   A lightweight web server, such as Gunicorn or uWSGI, should be used to minimize the overhead of serving HTTP requests.
*   A serverless function or background job should be used to handle the PDF conversion process, rather than running it in the main web server process. This reduces the load on the web server and allows it to handle more requests concurrently.
*   A cloud storage service, such as Amazon S3 or Google Cloud Storage, should be used to store the PDFs and text files. This reduces the storage requirements of the app and makes it more scalable.
*   A cache service, such as Redis or Memcached, should be used to store frequently accessed data and reduce the load on the database.
*   A performance monitoring tool, such as New Relic or Datadog, should be used to track the app's resource usage and identify any bottlenecks that may need to be addressed.

By following these strategies, the app should be optimized to run efficiently on Heroku, minimizing resource usage and maximizing performance. This will allows the app to scale to meet the needs of a large number of users without sacrificing speed or reliability.

Ongoing Maintenance and Support
-------------------------------

To ensure the long-term success of the app, it is important to provide ongoing maintenance and support. This may involve the following activities:

*   Monitoring the app's performance and resource usage using tools like New Relic or Datadog. This can help to identify any bottlenecks or issues that may need to be addressed.
*   Updating the app's code and dependencies as needed to fix bugs, add new features, or improve performance.
*   Providing customer support to help users with any issues they may encounter while using the app.
*   Backing up the app's data regularly to ensure that it is not lost in case of any unforeseen events.

By providing ongoing maintenance and support, the app can continue to meet the user's needs and remain a valuable resource for the community.

License
=======

This project is licensed under the [MIT License](LICENSE).

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

This project uses open source libraries with their own licenses. Please see the [LICENSE-3RD-PARTY](LICENSE-3RD-PARTY) file for more information.
