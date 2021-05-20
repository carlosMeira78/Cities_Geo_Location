# API Rest de Consulta de cidades do Brasil

Projeto que busca, principalmente, calcular a distância entre todas cidades do Brasil. 

## Requirements
> - **Linux ou Windows**
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
- [Data]
>
> For Linux:

> ```
> 	git clone cd ~/workspace/sql-paises-estados-cidades/PostgreSQL
docker run -it --rm --net=host -v $PWD:/tmp postgres /bin/bash
> ```
> > ```
> 	docker run -it --rm --net=host -v $PWD:/tmp postgres /bin/bash
> ```


> For Windows:
> ```
> 	git clone [cd ~/workspace/sql-paises-estados-cidades/PostgreSQL
docker run -it --rm --net=host -v $PWD:/tmp postgres /bin/bash
]> ```


> Ordinary:
> ```
> 	git clone [
psql -h localhost -U postgres_user_city cities -f /tmp/pais.sql
psql -h localhost -U postgres_user_city cities -f /tmp/estado.sql
psql -h localhost -U postgres_user_city cities -f /tmp/cidade.sql

psql -h localhost -U postgres_user_city cities

CREATE EXTENSION cube; 
CREATE EXTENSION earthdistance;
]
> ```

## Execução

Esse é talvez o tópico mais importante, faça com atenção.

Através das informações especificadas nele, outras pessoas poderam visualizar e testar o funcionamento da sua aplicação.

> Exemplo: 
>
> Após ter configurado o projeto e ter aguardado a instalação das dependencias de desenvolvimento, execute o comando:
> ```
> 	yarn start
> ```
> A aplicação estará disponível para visualização em seu navegador, caso isso não aconteça automaticamente abre o navegador no seguinte endereço: _localhost:3000_

## Funcionalidades

Imagine aqui que outra pessoa configurou e executou o seu projeto, apresente então as principais funcionalidade que seu projeto tem e onde encontrar, dessa forma ela vai conseguir testar e usar tudo o que foi desenvolvido.

Você ao fazer isso evita que o usuário da aplicação, por não ter conhecimento, pule ou não veja o que seu projeto é capaz de fazer.

> Exemplo: 
>
> Este projeto visa a funcionalidade de ser: 
> - Template de README.md em PORTUGUÊS - PTBR;
> - Artigo explicando e exemplificando tópicos de documentação;


## Testes

Sua aplicação contempla testes? Se sim, explique como executar os testes automatizados para este sistema; você também pode anexar aqui as capturas de telas (prints) dos testes que você fez ou de um determinado comportamento da aplicação.

Tipos de testes: 
- Unitários
- Performance
- Segurança
- Regressão

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
