# DataBase Migration With Liquibase

Automatic migration for creating student tables.


### Execution Instructions

In the liquibase-dev.properties y liquibase-dev.properties change the username, password and verify the url of your local database.



### Execution Instructions

**Developer**  
`liquibase --defaultsFile=liquibase-dev.properties update`

**Production**  
`liquibase --defaultsFile=liquibase-prod.properties update`