# 🎥 About cinema-app
This project is a basic implementation of a cinema-ticket online shop application, which is based on Spring, Hibernate, database usage and REST principles. 
Introduced authorization and authentication. Implemented global exception handler. All incoming and outgoing data are converted to JSON format.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
# 🎯 Goal
The aim of the project is to show possibility of creating Java-applications with combined usage of Spring and Hibernate and to simulate simple online-shop functionality.
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
# 🎦 Cinema-app features
Cinema app uses database to store information about users, tickets and movie sessions. It also has basic authentication and authorization features with two roles - admin and user.   
Every user has a shopping cart and orders.  
Movie session contains information about movie, cinema hall and showtime.  
Every ticket contains information about a movie session and user.
- User has an email and password. You can register new user(all roles) and find one by email(admin only).
- Movie has a title and description. You can add a movie into database(admin only) or get a list of movies from DB.
- Cinema hall has a capacity and description. Operations with cinema halls are similar to operations with movies.
- Movie sessions can be added, updated, deleted by admin. User can get a list of available movie sessions for desired date and movie.
- Shopping cart contains information about tickets user is willing to buy. User can add a ticket to shopping cart or get information about his shopping cart contents.
- Orders contain information about purchased tickets with order date and user to whom they belong. User can complete his order or get his orders list. Completing order will clean users shopping cart.
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
# 🌐 List of all endpoints
- POST: /register - all  
- GET: /cinema-halls - user/admin
- GET: /movies - user/admin  
- GET: /movie-sessions/available - user/admin
- POST: /cinema-halls - admin
- POST: /movies - admin
- POST: /movie-sessions - admin  
- PUT: /movie-sessions/{id} - admin
- GET: /users/by-email - admin 
- DELETE: /movie-sessions/{id} - admin
- GET: /orders - user  
- POST: /orders/complete - user  
- PUT: /shopping-carts/movie-sessions - user  
- GET: /shopping-carts/by-user - user

POST request example using Postman:
```
http://localhost:8080/movies - URL
{"title":"testMovie", "description":"test description"} - body;
```
You will also need to specify basic authentication login and password for currently logged-in user in authorization parameters.
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
# 🛠️ Technologies stack
- [x] Java 11
- [x] Hibernate
- [x] Spring Framework
- [x] REST
- [x] MySQL
- [x] Apache Tomcat 9.0.54 (to run app locally)

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
# 🧰 Installation and running
To run this project you will need to do these steps:
1. Install [MySQL](https://dev.mysql.com/downloads/) and [Apache Tomcat 9.0.54](https://tomcat.apache.org/download-90.cgi).
2. Create empty database.
3. Clone this project.
4. Edit database connection information(URL, username, password) in ```db.properties``` in ```resources``` folder:
``` java
#MySQL properties
db.driver=com.mysql.cj.jdbc.Driver
db.url=jdbc:YOUR DATABASE URL
db.user=YOUR USERNAME
db.password=YOUR PASSWORD
```
5. Add Tomcat to the running configuration of your project and use Tomcat application context.
6. Run project using previously configured Tomcat running configuration and login as admin(admin@i.ua | 888888) or user(user@i.ua | 000000).
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)