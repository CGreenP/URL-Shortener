# URL-Shortener
A URL Shortener With Node.js, Express, and MongoDB inspired by Web Dev Simplified.
* Video link- https://youtu.be/SLpUKAGnm-g
* Github link- https://github.com/WebDevSimplified/url-shortener

## Introduction:
In this project, we create a simple URL shortener using Node.js, Express, MongoDB, and EJS. We use the shortid module to generate unique identifiers for each URL and store them in a MongoDB database. We also keep track of the number of clicks for each shortened URL and display them in a table. We use EJS to render the HTML view and Bootstrap to style the user interface. We also implement a delete function to remove unwanted URLs from the database. Our URL shortener is a simple but functional web application that demonstrates the basic concepts of web development using Node.js and MongoDB.

## Features of Our Application
Some features are as follows:
* URL shortening: The application allows users to enter long URLs and generate short, easy-to-remember URLs.
* URL redirection: The short URLs generated by the application can be used to redirect users to the original long URLs.
* Click tracking: The application tracks the number of clicks on each short URL and displays it to the user.
* URL deletion: The application allows users to delete short URLs that are no longer needed.
* Database storage: The application uses MongoDB to store the full URLs, short URLs, and click counts of each URL.

## ARCHITECTURE
These are the architectural designs of our application which will give a basic understanding of workings by our application. Some of the designs are described in a summarized way by which you can understand the structure.
### Architecture of the Application
The application consists of three main components: the client, the server, and the database.
* The client is the web browser that interacts with the user and displays the web page. It sends requests to the server and receives responses from it. It also handles the user input and output, such as entering, viewing, and deleting URLs.
* The server is the Node.js application that runs on a local host and listens to a specific port. It handles the requests from the client and performs the logic and operations of the application. It also communicates with the database and sends responses to the client. It uses Express as the web framework and EJS as the templating engine.
* The database is the MongoDB database that runs on a local host and stores the data of the application. It contains a collection of documents that represent the URLs, with their full, short, and clicks fields. It uses mongoose as the object data modeling (ODM) library.

The application follows a request-response cycle, as shown in the following diagram:
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/11310300-14bd-4eb1-8111-8093b1f8a2c1)

#### Creating Short URL from Full URL
The user inputs the full URL into the input field on the index page. When the form is submitted, the full URL is sent to the server via a POST request to the "/shorturls" endpoint. The server then creates a new "urls" entity with the full URL and a generated shortened URL. The shortened URL is then displayed on the index page along with the full URL and the number of clicks.
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/d1c21365-40cb-43a3-aba5-844e065201fa)

#### Redirecting clients from Short URL to Full URL
When a user clicks on the shortened URL, a GET request is sent to the server with the shortened URL as a parameter. The server then looks up the "urls" entity with the matching shortened URL and redirects the user to the full URL.
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/85607600-0d51-4499-a597-ba4ca8e9c277)

#### Deleting URLS from database
When a user clicks the "Delete" button next to a URL on the index page, a DELETE request is sent to the server with the URL's ID as a parameter. The server then looks up the "urls" entity with the matching ID and deletes it from the database.
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/0bfc13c3-97dd-402c-9f4b-61c9fa7e9c24)

### Database Schema Design
For this application we have used MongoDB Database which is basically a NO-SQL based database. And it is very easy to use for a beginner start-up and also very easy to manage.
The database contains one collection called urls, which stores the documents that represent the URLs.
Each document has the following fields:
* full: a string that contains the full URL entered by the user. It is required and unique.
* short: a string that contains the short URL generated by the application. It is required and unique. It has a default value of shortId.generate(), which calls the shortid module to create a random and non-sequential identifier.
* clicks: a number that contains the number of clicks for the URL. It is required and has a default value of 0.
We have one entity, "urls," which has three attributes, "full," "short," and "clicks." The "full" attribute represents the full URL, while the "short" attribute represents the shortened URL, and the "clicks" attribute represents the number of clicks the shortened URL has received.

We have 1 table (collection) for our application are as follows:
* urls [shown below]

![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/5fe0d5e9-a4c3-4366-8c11-ed91be50bae7)

### Prerequisite
1. Download and Install NodeJS for development purpose.
Download Link: https://nodejs.org/en/download/
2. Download and Install VSCode for production/coding (you can use any text-editor).
Download Link: https://code.visualstudio.com/download
3. Download and Install MongoDB Compass for database purpose.
Download Link: https://www.mongodb.com/try/download/compass

Once you have installed MongoDB Compass, you can connect to your MongoDB host by either providing your connection string or specifying advanced connection options. Create a connection string. For that, you’ll need to enter the same URI as the URI entered in code in order to connect to the database. For our use case the URI would be mongodb://localhost:27017 and after that click the connect button.

![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/fc1a96a0-d109-4cd5-9b12-8e6ddcca6418)

4. Download and Configure Git-Bash in your system.
5. Now we have to open VSCode and select file -> open folder -> URL-SHORTENER.
8. And then we have to select that newly created directory.
9. Now we have to open a new terminal in VSCode. After opening that new terminal, we have to run some simple commands in it!
* Command to run the web application by running this command. **npm start**.
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/3451fc65-0cb9-4e9d-af8b-0e5f3cb6da34)

## METHODOLOGY
This is a section where the working and the final result for the application is written below. The exact details on how to use this application from the perspective of the user is given. Client Server Architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection. This system shares computing resources. Client/server architecture is also known as a networking computing model or client/server network because all the requests and services are delivered over a network.

### Creating Short URL from Full URL
User inputs the full URL into the input field URL on the index page http://localhost:5000/. When the form is submitted by clicking the Shrink button, the full URL is sent to the server via a POST request to the "/shorturls" endpoint. The server then creates a new "urls" entity with the full URL and a generated shortened URL. The shortened URL is then displayed on the index page along with the full URL and the number of clicks in table format.
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/9e87ff34-4ef1-4390-b4ca-7cfcb80d574a)
<p align="center">Index Page</p>
![image](https://github.com/CGreenP/URL-Shortener/assets/56307530/23bcc5a3-8ea4-4476-9ab7-694e7f0292c4)
<p align="center">Entering a URL to be Shortened</p>
