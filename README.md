# Spring Boot OAuth2 - Authorization

## Resource Server Application

* Create a maven project which will authenticate and return json data. Also we will be configuring the authorization server.

* Define the Spring Boot bootstrap class having the SpringBootApplication annotation.

* Define the model class Employee. We will be return this model class as JSON response.

* Define the controller that exposes a GET REST endpoint to return JSON as response.

* We will be configuring security. In this configuration we specify which urls are to be intercepted, and are to be accessed by which users and having which roles.

* We configure an authorization server using EnableAuthorizationServer annotation.

## Client Application

* We will create the client application. This application will ask the resource server we created above for JSON data. As explained previously we have assumed that this Client Application is already registered to the Resource Server, and has got the client id as 'javainuse' and secret key as 'secret'.

* Create the Controller class with the getEmployeeInfo method which returns a jsp page.

* Create a application.properties file
`[ * spring.mvc.view.prefix:/WEB-INF/jsp/ * spring.mvc.view.suffix:.jsp * server.port:8090 ]`

* At last create the Spring Boot Bootstrap class with SpringBootApplication annotation.

* Create the getEmployees.jsp using which we will POST a request to /authorize in form encoded url format.

### Getting the Access Token

* For getting the access token from the resource server the changes are only required at the client application end.

### Using the Access Token to get the JSON data

#### Resource Server Changes

* Resource Server module class allows any request with valid access token and scope to get the requested resource.

* Create a application.properties file
`[ * security.oauth2.resource.filter-order = 3 ]`

#### Client Application Changes

* Domain class Employee in the client application, similar to the resource server module.

* Client application using the access token as validation call the url to get the JSON data.

* Define the jsp named showEmployees to display the Employee info recieved.

### Run the Server and Client Application

* Run server `[SpringBootResourceServerApplication.java]`
* Run client `[SpringBootFormHandingApplication.java]`

### Look like attached image

![](img/1.png)

![](img/2.png)

![](img/3.png)

![](img/4.png)

![](img/5.png)

![](img/6.png)
