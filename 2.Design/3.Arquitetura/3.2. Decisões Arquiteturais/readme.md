### Decisões Arquiteturais


#### [Decisão Arquitetural 001] 

O Backend será desenvolvido utilizando NodeJS utilizando ExpressJS que é um framework baseado em javascript

#### Objetivo:

Permitir um desenvolvimento mais produtivo do software.


#### Motivação

 É possível o aproveitamento de conhecimento da linguagem tanto no front end quanto no backend

  - É um framework adequado para início de um projeto, pois apesar das poucas funcionalidades, elas executam muito bem o seu papel e exigem uma baixa curva de aprendizado.  

  - Possibilidade de dividir a aplicação em micro-serviços 

podemos utilizar o mesmo gerenciador de pacotes, no caso optamos utilizar o yarn que é mais performático que o npm
e oferece mais funcionalidades

-Arquitetura Event-Loop

 - Baseada em eventos(Rotas na maioria das vezes)
 - Call Stack - O node processa através de um loop eterno checando se existem novas funções disparadas pela aplicação que serão executadas em formato de pilha

- Node single-thread
 - C++ por trás com libuv - Permite a utilização multi-thread do processamento, aumentando o desempenho da call stack fornecendo um resultado mais rápido

 - Background threads

-Arquitetura Non-Blocking I/O
	É possivel manter uma conexão aberta a requisições permitindo utilização de recursos como websockets.

	
---------------------------------------------------------------------------------------------


#### [Decisão Arquitetural 002] 

 A arquitetura utilizada é a MVC que é dividida em três camadas lógicas: 

Apresentação (ReactJS),
lógica de negócio, e persistência de dados (NodeJS e Postgres). 

A camada de apresentação irá se comunicar apenas com a lógica de negócio presente no Backend, através de uma biblioteca chamada axios e apenas a lógica de negócio se comunica com a camada de persistência de dados utilizando o ORM Sequelize e o banco de dados Postgres.

#### Objetivos:

 Essa divisão diminui o acoplamento entre os elementos internos da arquitetura, facilitando o desenvolvimento e a manutenção;

#### Motivação:

Motivação: Projetar os elementos internos do sistema de modo que cada um pertença a apenas uma camada lógica ajuda a aumentar a coesão e diminuir o acoplamento. A coesão aumenta, pois cada elemento será desenvolvido com o objetivo de ser parte da apresentação, da lógica ou da persistência do sistema. Dessa maneira, cada elemento terá sua responsabilidade bem definida, mesmo que em alto nível. 


![MVC](./mvc.png)

---------------------------------------------------------------------------------------------

#### [Decisão Arquitetural 003] 

O Frontend será desenvolvido utilizando ReactJS que é uma biblioteca baseada em javascript

#### Objetivos:

Construir Interfaces, de forma componentizada utilizando o modelo de Single-Page Application, de modo a evitar 
carregamentos desnecessários da página, e obtendo mais perfomance e usabilidade

#### Motivação: 

	Organização excepcional do código utilizando Componentização, criando um conjunto de HTML, CSS e javascript isolando a lógica de diferentes partes sem que ela interfira 
  no restante do código da aplicação.

	Divisão de responsabilidades:

	Back-end: Regra de negócio
	Front-end: Interface

	Possibilidade de aproveitar o conhecimento do framework para desenvolvimento em mobile usando React Native que poderá consumir da mesma api do backend.

	Programação declarativa

