# Debate Web Application

This simple application was inspired by Dr. Jesse Hartloff at the University at Buffalo.  Dr. Hartloff wanted a debate application that allowed a user to propose a question and then allow users to see both sides of the debate.  Additionally, users could choose a side to a debate and then they would only be allowed to comment on that side.  Any user could create a debate and any user could comment on public debates.  There is also support for private debates that can only be found via the link.  Users are also able to register and login to the system to keep track of the debates that they keep.

The front-end of the application is written in ReactJS and communicates with the database via a REST API written in SparkJava.  The SparkJava API then communicates with a mySQL database.  This project was my final project for my Software Engineering class at the University at Buffalo in Spring 2019. For anyone wondering, I got an A. :+1:

##### To run the app locally:

1. Install Maven. https://www.baeldung.com/install-maven-on-windows-linux-mac

2. Install NPM. https://www.taniarascia.com/how-to-install-and-use-node-js-and-npm-mac-and-windows/

3. Install MYSQL. https://dev.mysql.com/doc/refman/5.6/en/installing.html
    -Make sure to remember what root password you used!!

4. After you cloned the repo, go into the spark folder.  Create a file called config.properties.  It should have the format below.  Update the database username and password to match your mysql username and password.  Modify salt to be anything.

```#debate app properties
database.connectionString=jdbc:mysql://localhost:3306
database.username=root
database.password=password
password.salt=S;dcUk>/uRKTK;mC8g%(z%2B0n#C|m@~D#hzhD.WN8=m.c)gM+{j|V8H
email.smtp.port=587
email.smtp.fromAddress=email@email.com
email.smtp.fromName=My Name
email.smtp.host=<SMTP HOST>
email.smtp.username=<SMTP USERNAME>
email.smtp.password=<SMTP PASSWORD>
```

5. From the spark folder type ```mvn clean install```.  This will build a jar file in the /spark/target/ folder.  Once it is finished run ```java -jar ./target/debate-app-1.0-jar-with-dependencies.jar``` to start the backend.  You have to leave this window open!  You should now have a running backend at http://localhost:4567/.  You can verify it is working by visiting http://localhost:4567/debates/recent.

6. We need to give the database some test data.  You can find a sample script in the spark folder called test.sql.  If you run ```mysql -u <USERNAME> -p < example.sql``` from the spark folder you will import some dummy data.

7. From the react directory run ```npm install```, then run ```npm start```.  You have to leave this window open!  Your browser should open to http://localhost:3000 automatically.  If it doesn't, just open a browser window and go to that URL.  You should now see the running React app!
