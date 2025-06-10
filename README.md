
# DataBase Migration With Liquibase
Automatic migration for creating student tables.


## Setup
### Install Liquibase
**Mac Installation**  
`brew install liquibase`

**Windows Installation**  
`https://github.com/liquibase/liquibase/releases/tag/v4.32.0`

If necessary, add liquibase to the path.  


### Install SQLDeveloper  
**Download link**
`https://www.oracle.com/mx/database/sqldeveloper/technologies/download/`


### Install Docker Desktop
**Download link**  
`https://www.docker.com/products/docker-desktop/`


## Instructions
### Create DataBase Container
From the following code, change <your password> to the password you want to use to connect to your local database.

**Create oracle free faststart**  
`docker run -d -p 1521:1521 -e ORACLE_PASSWORD=<your password> gvenzl/oracle-free:slim-faststart`

Run the command in the Docker Desktop terminal and wait until the database is built.


### Create Users In Local DataBase
Open SQLDeveloper and connect to your local database by entering the password you used to create the container.

Create the two users to be able to add the tables with liquibase

Connect to your local database and create the users in the folder located at the bottom by right-clicking on it and clicking on add user.

Create your user and write down both the username and password to use later in the repository code. This must be done for both DEVELOP and PRODUCTION. Users must have all the permissions granted in the roles tab.


### Code Execution Instructions
In the liquibase-dev.properties and liquibase-dev.properties change the username, password with those you previously noted and verify the url of your local database.

In the terminal run the following commands.

**Developer**  
`liquibase --defaultsFile=liquibase-dev.properties update`

**Production**  
`liquibase --defaultsFile=liquibase-prod.properties update`


### What Should Be Shown
In the DEVELOP and PRODUCTION users, the new students table should be displayed. If it is not displayed, try disconnecting and reconnecting to the local database.
