# API

A construção da API da aplicação se baseia no método Rest utilizando o Nest.js como Back-end na construção das Models, Services e Controllers do projeto em conjunto com o Swagger para testar cada rota montada para API.

A API dentro do Swagger é dividida em vários Schemas que favorecem o funcionamento de toda a aplicação.

<figure><img src="../.gitbook/assets/schemas.png" alt=""><figcaption></figcaption></figure>

Certos componentes das rotas necessitam de uma chave de autorização para que o usuário possa acessar a requisição de cada rota. Para ter esse acesso é necessário que o usuário crie sua conta para poder fazer o login no Swagger e através do token que o mesmo recebe ao realizar o login, poder ter acesso a alguma das rotas ao colar ela na opção de Authorize.&#x20;

<figure><img src="../.gitbook/assets/imagem_2022-10-21_220329995.png" alt=""><figcaption></figcaption></figure>

Certas rotas vão ser obrigatórias ter acesso de administrador dentro do sistema caso queira acessa-las. &#x20;
