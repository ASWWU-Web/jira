# Jira Software
The Jira Software Docker Compose file and other information for setting up ASWWU's Jira instance.

## Installation
## Database server
Jira has specific configuration requirements for its database server. In the README for the mysql repository, there are instructions for modifying the ``my.cnf`` file and setting those settings properly.

## Database
Jira needs a database to run on in the MySQL server. Yo ucna setup one properly with the following commands.

Create the database:
```
mysql> CREATE DATABASE jira CHARACTER SET utf8mb4 COLLATE utf8mb4_bin;
```

Create the Jira user with proper permissions, be sure to change ``PASSWORD`` to something more secure.:
```
mysql> GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,REFERENCES,ALTER,INDEX on jira.* TO 'jira'@'%' IDENTIFIED BY 'PASSWORD';
```

Clear the permissions:
```
mysql> FLUSH PRIVILEGES;
```

You can now begin the setup process for jira and connect with the databse credentials.

## Jira server
You can startup the jira server using the following command:

```
$ docker-compose up -d
```

This will pull the necesary images and start the server.
