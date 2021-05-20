# API Rest - Looking for brazilian cities and its distances

The goal of this Project is to calculate the distance between all cities in Brazil.

## Requirements
> - **Linux or Windows**
> - **Git**
> - **Java 8 ou superior**
> - **Docker**
> - **IntelliJ Community**

## DataBase
 **Postgres**
- [Postgres Docker Hub](https://hub.docker.com/_/postgres)

> ```
> docker run --name cities-db -d -p 5432:5432 -e POSTGRES_USER=postgres_user_city -e POSTGRES_PASSWORD=super_password -e POSTGRES_DB=cities postgres
> ```


## Populate
- [Data](https://github.com/chinnonsantos/sql-paises-estados-cidades/tree/master/PostgreSQL)

> For Linux:

> ```
> 	cd ~/workspace/sql-paises-estados-cidades/PostgreSQL
> 	
> 	docker run -it --rm --net=host -v $PWD:/tmp postgres /bin/bash

> For Windows:
> ```
> 	cd ~/workspace/sql-paises-estados-cidades/PostgreSQL
> 	
> 	docker run -it --rm --net=host -v C:\Users\...\PostgreSQL/tmp postgres /bin/bash

> Ordinary:
> ```	
> 	psql -h localhost -U postgres_user_city cities -f /tmp/pais.sql
> 	psql -h localhost -U postgres_user_city cities -f /tmp/estado.sql
> 	psql -h localhost -U postgres_user_city cities -f /tmp/cidade.sql
> 	psql -h localhost -U postgres_user_city cities
> 	
> 	CREATE EXTENSION cube; 
> 	CREATE EXTENSION earthdistance;

- [Postgres Earth Distance](https://www.postgresql.org/docs/current/earthdistance.html)
- [Earthdistance--1.0--1.1.sql](https://github.com/postgres/postgres/blob/master/contrib/earthdistance/earthdistance--1.0--1.1.sql)
- [Operador <@>](https://github.com/postgres/postgres/blob/master/contrib/earthdistance/earthdistance--1.1.sql)
- [PostgresCheatSheet](https://postgrescheatsheet.com/#/tables)
- [DataBase Geometric](https://www.postgresql.org/docs/current/datatype-geometric.html)

## Access

> ```
> docker exec -it cities-db /bin/bash
> 
> psql -U postgres_user_city cities
> ```

## Query Earth Distance
 **Point**

> ```
> select ((select lat_lon from cidade where id = 4929) <@> (select lat_lon from cidade where id=5254)) as distance;
> ```

 **Cube**
> ```
> select earth_distance( ll_to_earth(-21.95840072631836,-47.98820114135742), ll_to_earth(-22.01740074157715,-47.88600158691406)) as distance;
> ```


## Spring Boot
- [Start Spring](https://start.spring.io/)
- Java 8+
- Gradle Project
- jar
- Spring Web
- Spring Data JPA
- PostgreSQL Driver

 **Spring Data**
- [JPA Query Methods](https://docs.spring.io/spring-data/jpa/docs/current/reference/html/#jpa.query-methods)
>
 **Properts**
- [Appendix Application Properties](https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html)
- [Jdbc Database Connectio](https://www.codejava.net/java-se/jdbc/jdbc-database-connection-url-for-common-databases)

>
 **Types**
- [Json Types](https://github.com/vladmihalcea/hibernate-types)
- [User Types](https://docs.jboss.org/hibernate/orm/3.5/api/org/hibernate/usertype/UserType.html)


## Code Quality
 **PMD**
- (https://pmd.github.io/pmd-6.8.0/index.html)

 **Checkstyle**
- https://checkstyle.org/
- https://checkstyle.org/google_style.html
- https://google.github.io/styleguide/javaguide.html

> ```
> wget https://raw.githubusercontent.com/checkstyle/checkstyle/master/src/main/resources/google_checks.xml
> ```

## Checks

**Access extension Postman from your computer and execute the following comands:**

- To Find all the countries - localhost:8080/countries
- To Find all the cities - localhost:8080/cities
- To Find all the states - localhost:8080/states
- To look for a specific country - localhost:8080/countries/... (choose an Id)

## Author

> - **Carlos Meira** - [Github](https://github.com/carlosMeira78)


## Thanks 

You never walk alone! 
This project was realized just because I´ve had help from DIO and programing friends like Caio Moreira.

- [DIO - Digital Inovation One](https://web.digitalinnovation.one/home)
- **Caio Moreira** - [Github](https://github.com/caiomcs04)



