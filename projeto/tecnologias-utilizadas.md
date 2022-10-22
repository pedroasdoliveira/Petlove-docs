# Tecnologias utilizadas

## 💻 Website

### Next.js

Toda a infraestrutura da parte do cliente da aplicação foi utilizando o Nextjs, um framework da biblioteca React com o intuito de fornecer um suporte maior em desempenho, renderização de páginas e auxiliar no desenvolvimento de uma aplicação mais performática para os sistemas de buscas.

### Chakra-UI

Trata-se de uma biblioteca de estilização e de componentes para aplicações React. A maioria dos componentes HTML são baseados dos Chakra-UI para a construção e estilização de cada parte do projeto. A biblioteca também oferece diferentes tipos de componentes pre prontos para a utilização do projeto, como modais, menus etc, além de auxiliar na responsividade da aplicação em diferentes dispositivos. Já na parte mais de desenvolvimento, o Chakra também contribui na disponibilidade de hooks para estilização e funcionalidades, como os modos de White e Dark Mode.

### Yup e React Hook Form

Tratam se de duas bibliotecas separadas para a construção de formulários como os de Registro e Login que trabalham em conjunto. A React Hook Form tem o intuito de auxiliar na construção de formulários e campos de inputs para cada funcionalidade. Já a Yup cuida mais da tratativa de cada campo caso o usuário digite algo errado no campo ou não siga com as instruções obrigatórias para o cadastro.

### Swiper

Essa biblioteca para estilização auxilia na construção dos carrosséis de informações que contém no projeto para visualizar cada elemento por vez ao trocar.

### Recharts

Biblioteca utilizada para a construção dos diferentes gráficos dentro da aplicação para a visualização dos resultados.

### React Hot Toast

Biblioteca React para o envio de notificações dentro da aplicação.

## ⚡ API

### Nest.js

Nest.js é um framework Back-end baseado no Express.js para estruturas MVC, MVP e para construção de APIs. Outra vantagem é a integração com sistemas de autenticação em diferentes funções de service para API, além de ele facilitar o desenvolvedor na construção de models e outras funções na opção da CLI da aplicação.

### OAuth

Para acessar as informações armazenadas na API, foi usado o OAuth. Este é um protocolo de autorização para API's web voltado a permitir que aplicações cliente acessem um recurso protegido em nome de um usuário.

### Swagger

Essa ferramenta permite a visualização de todas as rotas dentro da API Rest do projeto e com a possibilidade de testa-las diretamente através de cada requisição.&#x20;

## ⚙ Servidor

### Axios

O axios é a biblioteca que cuida da parte de integração entre nosso Front-end com o servidor do Back-end para o envio de requisições e recebimento das informações para renderizar na tela e nos gráficos as informações de cada rota da API.

### Nodemailer

&#x20;O uso dessa biblioteca permite o envio de emails criados para usuários que cadastraram seus emails de forma correta, para o envio de notificações e de confirmação de senha para entrar na aplicação.

### Prisma ORM

O Prisma permite realizar a conexão e enviar as modificações em do servidor para armazenar em nosso banco de dados cadastrado. Através dele, toda a nossa configuração do service e do controller com a API fica em volta do Prisma para caso aconteça um novo cadastro, edição ou exclusão de alguma informação, como os usuários, ele possa transferir direto para o banco de dados.

### PostgreSQL&#x20;

O PostgreSQL atua como o banco de dados principal da aplicação. Todas as informações que são enviadas ficam salvas no PostgreSQL para serem utilizadas a qualquer momento. Por se tratar de um banco SQL, com ele é possível fazer diferentes relações entre colunas em nossa aplicação com o auxilio do Prisma.

## 🔧 Configurações de Desenvolvimento

### TypeScript

Toda a configuração e funções do projeto são baseadas em Typescript para auxiliar no desenvolvimento da aplicação como um todo, como na importação correta de cada função e nas tipagens das funções assíncrona que espera algum valor que seja do servidor ou API.

### Jest

Jest é a biblioteca para a criação de testes de aplicações em nosso projeto Front-end. Toda a configuração já implementada encontra-se no arquivo de configuração da ferramenta (jest.config.ts) para a realização dos testes na aplicação.

### React Testing Library (RTL)

Essa biblioteca trabalha em conjunto com o Jest para testar os componentes das páginas na aplicação React.

### Plop

Essa biblioteca simples permite a criação de componentes ou páginas no Front-end através de comandos pela CLI do projeto.

## 🚀 Deploy
