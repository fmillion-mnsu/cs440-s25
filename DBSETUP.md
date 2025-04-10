# Setting Up Database Servers

This document will provide you guidance on setting up and using all of the database servers we have covered in class using [Docker](https://www.docker.com).

The examples given here will use the [Docker Compose](https://docs.docker.com/compose/) format to specify configuration for the containers in a configuration file, rather than you needing to manually type out and modify the long Docker commands yourself. With Docker Compose, you can define all of your containers in one place and issue a single command to download and start up the containers all at once.

## Docker Compose

A Docker Compose "stack" is defined in a `compose.yml` file. The `compose.yml` file specifies each container that you want to run in the stack.

If you need a refresher on how the YAML format works, [here is a YAML cheat sheet](https://quickref.me/yaml.html).

All Compose files contain at least a single section called `services`. At the top of a Compose file, you'll typically see this line:

`services:`

(Remember that YAML uses indentation, like Python, to indicate which "level" an element is at. The line `services:` also indicates that the top-level object of the YAML file is a key-value store, much like a typical JSON file.)

The examples below will be given as individual service sections that you can place underneath the `services:` section. You can simply copy and paste the definition for each database service you intend to use into your Compose file, one after the other, after starting out with `services:` on its own line.

## Relational Databases

These are traditional relational databases that you may already be familiar with. 

### MySQL

MySQL is a very popular database engine that is maintained by Oracle. Due to some concerns about Oracle and its stewardship of MySQL, given that Oracle markets and sells its own very expensive and popular database engine, some developers forked the MySQL code into "MariaDB". MariaDB is protocol-compatible with MySQL, so you can use either one you like.

Choose only one - if you decide to use both (for some reason) you'll need to change the port on one instance.

MySQL:

```
  mysql:
    image: mysql
    ports:
      - 3306:3306
    volumes:
      - ./mysql:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: SetThisToSomethingElse!
```

MariaDB:

```
  mariadb:
    image: mariadb
    ports:
      - 3306:3306
    volumes:
      - ./mariadb:/var/lib/mysql
    environment:
      MARIADB_ROOT_PASSWORD: SetThisToSomethingElse!
```

#### Management tools

The official MySQL management tool is called [MySQL Workbench](https://www.mysql.com/products/workbench/). This tool also works with MariaDB (as do most all other MySQL tools.)

You can also try [HeidiSQL](https://www.heidisql.com/), which supports MySQL along with several other relational databases. It is more lightweight than MySQL Workbench, but requires Windows.

[Azure Data Studio](https://azure.microsoft.com/en-us/products/data-studio) runs on all platforms and supports MySQL via plugins. It is based on the Visual Studio Code engine.

### Microsoft SQL Server

SQL Server is Microsoft's relational database offering. It is known for being tighly integrated with the .NET Framework, allowing for scripts to be written and compiled into .NET IL code. It also supports the proprietary `T-SQL` design for writing stored functions and procedures.

```
  mssql:
    image: mcr.microsoft.com/mssql/server
    ports:
      - "1433:1433"
    volumes:
      - ./mssql:/var/opt/mssql
    environment:
      ACCEPT_EULA: y
      SA_PASSWORD: ChangeThisToSomethingElse!
```

#### Management tools

The official management tool for SQL Server is [SQL Server Management Studio](https://learn.microsoft.com/en-us/ssms/download-sql-server-management-studio-ssms). It is based on the full desktop Visual Studio engine and requires Windows.

You can also try [HeidiSQL](https://www.heidisql.com/), which supports Microsoft SQL Server along with several other relational databases. It is more lightweight than SQL Server Management Studio, and also requires Windows.

[Azure Data Studio](https://azure.microsoft.com/en-us/products/data-studio) runs on all platforms and supports SQL Server natively. It is based on the Visual Studio Code engine.

### PostgreSQL

PostgreSQL is another popular SQL engine that is offered as part of many cloud hosted database services.

```
  postgres:
    image: postgres
    shm_size: 128mb
    ports:
      - 5432:5432
    volumes:
      - ./postgres:/var/lib/postgresql
    environment:
      POSTGRES_PASSWORD: ChangeThisToSomethingElse!
```

#### Management tools

[PGAdmin](https://www.pgadmin.org/) is the most popular PostgreSQL management tool, offering native support for Postgres and a complete user interface.

You can also try [HeidiSQL](https://www.heidisql.com/), which supports PostgreSQL along with several other relational databases. It is more lightweight than PGAdmin, but requires Windows.

## MongoDB

MongoDB is a popular document-oriented NoSQL database.

