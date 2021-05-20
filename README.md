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

**Access extension Postman and execute the following comands:**

- To Find all the countries - localhost:8080/countries
- To Find all the cities - localhost:8080/cities
- To Find all the states - localhost:8080/states
- To look for a spacific country - localhost:8080/countries/... (choose a Id)

Dentre outros...
> Exemplo de comando para execução de testes em uma aplicação:
> ```
> 	yarn test
> ```

## Links

Mesmo que as informações possam estar sendo apresentadas no seu código, pode ocorrer de algumas pessoas não terem total entendimento sobre o que foi proposto ou determinados termos técnicos, você pode incluir um resumo dos links mais úteis para leitura dessas termos, por exemplo.

> Exemplo: 
> - [Guia de Markdown](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open)
> - [Como formatar o Readme?](https://medium.com/@raullesteves/github-como-fazer-um-readme-md-bonit%C3%A3o-c85c8f154f8#:~:text=md%20%C3%A9%20um%20arquivo%20markdown,tags%20tamb%C3%A9m%20funcionam%2C%20veremos%20adiante.&text=Basta%20copiar%20o%20que%20o,e%20colar%20no%20README.md.)


## Contribuições

Seu projeto pode receber contribuições da comunidade? Se sim, utilize esse tópico;
aqui você coloca as informações resumidas de como a pessoa poderá o ajudar com o projeto.

> Exemplo:
> - Para contribuir com esse projeto, fork este projeto, faça as modificações que tens desejo e crie um pull request; veja as instruções detalhadas no arquivo _CONTRIBUTING.md_.

## Autores

Informe o nome das pessoas envolvidas no desenvolvimento do projeto e se quiser atribua as respectivas redes sociais para contato da comunidade;

> Exemplo (Deste projeto):
> - **Lucas Anderson Lima** - Idealizador e Escritor da Documentação - [Github](https://github.com/LuAnderson) | [Site](http://lucasanderson.com.br/)


## Licença 

Existem vários tipos de licença open souce, para saber qual condiz mais com o seu projeto e até mesmo entender mais detalhadamente, recomendo verificar os tipos no seguinte site: [Escolha uma Licença](http://escolhaumalicenca.com.br/).

> Exemplo: 
> 
> MIT License (MIT)

## Agradecimentos 

Aqui, sinta-se a vontade a agradecer quem você desejar, tenha sido uma pessoa que a incentivou no projeto, inspirador, colaborador, amigos, etc.  

> Exemplo: 
> 
> Comunidade Front <3

---
Autor ❤ [Lucas Anderson Lima](http://lucasanderson.com.br/)
