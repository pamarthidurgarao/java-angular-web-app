## Spring boot app with Angular 4 client embedded

The frontend-app is gotten from :https://github.com/creativetimofficial/material-dashboard-angular

## Description

The project is used to develop the client in the **frontend-app** folder with the __angular-cli__, and the **java backend** with the __maven spring boot project configured__.
For this, import your client (frontend-app) in the angular/typescript IDE (i.e. __visual studio code__) and your java backend in __Eclipse__

## functional informations

The steps to build the jar are defined in the pom.xml file. The project builds the frontend with the output folder **frontend-app/dist** and copies it in the __src/main/resources/static__ folder in order to load the client in the spring boot home page together the java services.
The port information is stored in **src/main/resources/application.properties** file in the __server.port__ property.

### Prerequisites

* Angular cli:

```
npm install -g @angular/cli
```

* JDK 8

* The last Node.js version

* MAVEN (to use **mvn** command else use in windows ./mvnw.cmd or in linux ./mvnw instead)

* IDE ( i.e. Eclipse for java and visual studio code for typescript/angular projects)

### Live

```
mvn clean spring-boot:run
```
Open browser on localhost:8081

### Build and run

```
mvn clean package
```

After:

```
java -jar target/*.jar
```
Open browser on localhost:8081

### Electron (not work with electron-packager )

Move __app.jar__ in electron-app folder and in this run **electron main** after **npm i electron -g**. 
The port is specified in the __electrona-app/index.html__.

IN DEVELOPMENT

### Deploy jar on heroku 

Create an account on keroku (https://www.heroku.com/)

After install the __heroku-cli__

```
npm install -g heroku-cli
```

Then:

```
heroku plugins:install heroku-cli-deploy

heroku create spring-boot-angular-app2  --no-remote

```

To deploy the jar file:

```
heroku deploy:jar target/app.jar --app spring-boot-angular-app2
```

View in : https://spring-boot-angular-app2.herokuapp.com/.

### Live demo heroku deployed jar

A demo is on https://spring-boot-angular-app.herokuapp.com/
