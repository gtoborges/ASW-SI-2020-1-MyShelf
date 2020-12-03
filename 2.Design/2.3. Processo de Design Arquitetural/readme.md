# Design Arquitetural

## Do back-end

Seguindo o padrão de programação com o node, o design e a organização dos arquivos são divididos por interesses. 
Assim, teremos uma divisão de pastas com os arquivos e suas funções de acordo com as suas funcionalidades.


De modo inicial, definimos aqui que dividiríamos os arquivos na seguinte estrutura:

```bash
/backend-end
├── /src
│   └── /app
|   |   └── /services
|   |   └── /middlewares
|   |   └── /models
|   └── /config
|   └── /database
|   |   └── /migrations
|   └── routes.js
|   └── app.js
|   └── server.js <= entry point
└── package.json

```

Tendo como o entry point (o ponto de partida inicial do server), o arquivo server.js. 
Dele, são importadas os outros arquivos. O fluxo principal na nossa aplicação seria:
 - server.js > app.js (configurações do server) > routes.js (definição das rotas) > middlewares/services.js (regras de negócio) e models.js (representação das tabelas do banco de dados)
 
 Os models são arquivos que representam as tabelas dos bancos de dados. Portanto, poderiam ficar na pasta /src/database já que estão relacionados
 com o banco de dados. Porém optamos por deixarmos ao lado dos services, pois entendemos os models como uma extensão dos services (que usarão os models para a persistência dos dados).
 
 O arquivo app.js contém as importações das rotas que estão em routes.js, e cada rota chama suas funções que irão ler, criar, atualizar e deletar 
 (que são as funções contidas em services.js). E para facilitar a organização, os arquivos de services são separados de acordo com as entidades 
 do sistema que eles tratam (usuarios, livros, etc). O mesmo pode ser feito com os arquivos de rotas, caso a complexidade do sistema aumente.
 
 
 Os outros arquivos manteremos separados (configurações do ORM sequelize, etc), para não se misturarem com os demais arquivos do sistema.
 
 ## Do front-end
 
 ```bash
/front-end
├── /src
|   └── /components
|   └── /pages
|   └── /routes
|   └── /services
|   └── /store
|   
└── package.json

```
 
 Aqui, iremos organizar os nossos arquivos de acordo com suas funcionalidades:
  - Components: são os componentes do sistema, como por exemplo: o formulário de cadastro de um novo livro, ou um livro
  - Pages: são as páginas do sistema, que são compostas da importação de um ou mais componentes
  - Routes: definição das rotas e páginas que são chamadas em cada rota
  - Services: configuração dos arquivos para a comunicação com o back-end
  - Store: de maneira mais simples e abstrata, é uma fonte de dados, que serve para a comunicação entre componentes
  - Styles: configurações e definições do css (estilização dos componentes ou páginas)
  
 
 
