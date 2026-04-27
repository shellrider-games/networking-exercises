# Assignment 2

Complete the exercises in this assignment.
Hand in a protocol documenting your steps while solving the exercises. On top of the protocol you must include:

 - Your name
 - Your student identification number (The one starting with cc)
 - Date you did the exercises on

Please hand in the protocol as a PDF including clearly labeled sections for each exercise.

In this assignment you will be using the `curl` tool (if you are working on Windows make sure to type `curl.exe` instead of just `curl`, the latter maps to a different tool). For every exercise please include:

 - The `curl` command used for the task
 - The relevant output
 - A short interpretation of the output

The target web server for this exercise is reachable at: https://lbbeckerg-11016.node.ustp.cloud

Do not try to hack the server, this is not the cybersecurity part of the lecture!

 ## Exercise A - Reading responses

### A.1
 Use `curl` to request `/` and make sure the response headers are included in the output (`-i` flag for response headers).

Answer the following questions:
 - What status code do you receive?
 - What `Content-Type` does the server return?
 - What kind of document is returned?

### A.2

Use `curl` to request `/info`. First request it without explicitly setting `Accept` headers then request it with different `Accept headers`. (Example `curl -H "Accept: bla/blub" http:example.com`)

Try at least these:
- `text/plain`
- `text/html`
- `application/json`
- `application/xml`

What changes for these different requests? What are the different status codes for the request and what do they mean?

## Exercise B - the `/messages` endpoint

### B.1

The `/messages` endpoint accepts:
 - `application/json`
 - `application/x-www-form-urlencoded`

 Read from the `/messages` endpoint and try to get:

 - HTML response
 - JSON response

### B.2

Create a new message by sending URL-encoded form data to /messages. 
(the `-X` allows you to set the HTTP method while the `-d` flag allows for setting data)

The endpoint requires the following fields:
 - title
 - content

After sending the message explain the response and request /messages again with a GET to verify your message appears.

### B.3

Do the same as in B.2 but send the data as JSON this time.

### B.4
Send an invalid request to /messages!

For example:
 - missing `title`
 - missing `content`
 - unsupported `Content-Type`

What status code do you get? What error message does the server return? Why did the request fail?

## Exercise C - The `/books` API

The server provides a small API for managing books.

A book consists of the following fields:
 - `title`
 - `author`
 - `year`

For this exercise, you are expected to figure out and use the correct `curl` commands for creating, reading, updating and deleting books.

### C.1

Create a new book entry on the server.

The request must include:
 - `title`
 - `author`
 - `year`

### C.2

Read the book you created in C.1 from the API.

Use the id returned by the server in the previous task.

Answer the following questions:
 - Which HTTP method did you use?
 - What status code did the server return?
 - Does the response contain the same data you originally sent?

### C.3

Update the book you created before.

Change at least one of the fields:
 - `title`
 - `author`
 - `year`

Can you see that your updated data was stored correctly?

### C.4

Delete the same book from the API.

After sending the request, answer the following questions:
 - Which HTTP method did you use?
 - What status code did the server return?
 - Does the server return a response body?
 - What does this status code mean in this context?

### C.5

Try to request the same book again after deleting it.

Answer the following questions:
 - What status code do you get now?
 - What does the response body say?
 - Why is this result correct?

## BONUS

Use any of your applications from another class and debug it using `curl`. Can you write a short script in a language you like (bash, PowerShell, ...) that automatically checks if your backend application works correctly? How could this approach help you during your project work so that you do not need to manually test your application after every change?