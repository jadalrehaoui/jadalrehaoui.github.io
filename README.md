# jadalrehaoui.github.io


**Professional Self-Assessment**

I have been in the computer science program since September 2021. While I already had a bachelor’s degree in information and communication technology, I always wanted a ticket to enter the programming world and become a software engineer. I have learned that there are many that coding is just a tool and what really makes it shine it is planned and designed in a good way. I also learned to keep in mind security, portability and maintainability when developing applications. 

As a computer science fresh graduate, I aim to work as a software engineer. To show off my skills, I am going to work on designing applications and software I have in my mind and share them on my ePortfolio for employers to get to know what I can do. 

**Application Breakdown**

The artifact I chose is a web-application for a travel company. The web application is a multi-tier application that employ databases, servers and HTML. It consists of the following:
*	API server
*	Front end server
*	Database
*	Content Management system

*API Server*

The API server is responsible to listen to request coming from the content management system and response with the data requested. It is built on top of the NodeJS framework using ExpressJS. All the requests handled are HTTP requests and it also authenticates users.

*Front End Server*

The front end is built using the angular framework. It is responsible to make HTTP requests to the API server, handle responses and render the HTML pages with the respective data coming from the API. 

*Database*

The database is MongoDB, locally installed and ran. We chose MongoDB as it is easy to learn and reliable. MongoDB is only connected to the API Server using the npm package mongoose, which also helps me query the database from the server with a cleaner and reliable code.

*Content Management System*

The content management system is built using the angular framework. It is responsible to perform requests and handle responses when data is needed. It is also responsible for rendering what the user can see when they want to add/update/delete/read data from the database. 

**Software Design and Engineering**

*System Architecture*

The architecture implemented in this project is a client-server one. The server responsible for managing REST APIs and the client responsible to rendering the views to the user. 
![image](https://github.com/jadalrehaoui/jadalrehaoui.github.io/blob/main/clientServerArch.png)
The front end can be accessed by anyone with an internet connection. It is where Travlr markets their deals and trips. The content management system on the other hand, can be accessed from anywhere too but authentication is required. In order to be authenticated, only admins on the system can create new accounts and share them with authorized users. There is no register page for the CMS. 
![image](https://github.com/jadalrehaoui/jadalrehaoui.github.io/blob/main/Architecture.png)

In this phase, I enhanced the design in the following manners: 
*	Converted the front end from a standalone NodeJS/ExpressJS server to angular.
*	Containerized each endpoint of the system isolating it.
*	The API server is the only entity connected to the database and I restricted access to the database from anywhere other than the API server.

**Algorithms and Data Structure**

*Pattern*

In this project I employed the MVC pattern, that consists of Models, Views and Controllers. 
This pattern is not only employed to make working on a project easier, but it also tells other developers how the project is divided and where they can find code to refine and update.
Here’s a visualization of how MVC work here:

![image](https://github.com/jadalrehaoui/jadalrehaoui.github.io/blob/main/Sequence%20Diagram.png)

*Model*

The model for this project is the entity saved in the database. It is a schema that we specify for the type and information needed in a document in the database.

*Controller*

This is where the logic happens, the controller is the handler of a route. When a route is accessed the controller function is ran and the response is given back. 

*View/Response/Presenter*

For this project, all the views are managed with angular, however the API server respond back to the request with JSON objects. These objects are the data needed to present the views written with angular.

**Authentication**

While developing this application, I was always ensuring to follow well known algorithms to make things work as they should. For example, the authentication process is a very common process in almost every application out there so why reinvent the wheel? I used JWT (JsonWebToken) a package from npm to sign the users. My authentication process does not require users to sign out, however each user signed in has a limited time that we can configure.

Here's a flowchart to visualize how authentication works in this application. This model is simplified, however in the code this is what passport (an npm package) does in the background.
![image](https://github.com/jadalrehaoui/jadalrehaoui.github.io/blob/main/LoginProcess.png)

**Databases**

As mentioned before, the database used for this project is MongoDB. MongoDB is a popular NoSQL, document-oriented database that offers advantages over traditional relational databases.
It is known for having high scalability, flexibility, and performance.
For this project, I ensured that data updates and creations are traceable. I added fields for the documents designed like: 
*	Created timestamp.
*	Updated timestamp.
*	Created By.
*	Updated By.
These fields serve like metadata, by looking at them we can know who created the data and who updated it. 

On the other hand, I also added a deleted field for the documents that indicate whether the data is deleted or not. This field helps the system archiving deleted data for a little period of time before deleting them from the database. 

Delete queries are not executed once the client perform a delete request, however they are tagged as deleted and after a period of 1 week the system will clean itself by deleting all the document tagged as deleted.

**Other enhancements**

*Docker*

I used docker to create and manage containers for the services required by this application. Like the MongoDB database, a container is created for it and configured to be isolated from anything else. The API server is also a separate container running independently and handling requests when needed on port 80.

*Code Documentation*

I made sure the code I wrote is well documented and clear. I used CamelCase for the whole project to keep consistency. I also made sure to name variable in a reasonable manner so that others know what this variable is for without digging deep into the code. 

*Security*

Because I finetuned the system design, the application became more secure because the data is isolated and only some pre-defined queries can be executed from the API Server.

*Flexibility and future add-ons*

Because the application is now designed the way it is, it is easier to add a mobile or desktop application to access the data needed. To do that we only need to design the new application and code its views. 

**Code Review**

Please refer to the video attachment submitted along with this file.
![image](https://github.com/jadalrehaoui/jadalrehaoui.github.io/assets/64440563/067cb9fe-6680-426c-8e39-14ae1b279929)
