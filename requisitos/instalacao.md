# 🚀 Instalação

## Clonando e rodando o projeto

### Front-end

HTTPS:&#x20;

```
https://github.com/pedroasdoliveira/petlove-project-frontend.git
```

GitHub CLI:

```
gh repo clone pedroasdoliveira/petlove-project-frontend
```

#### Instalação

Com o projeto clonado na maquina, execute o comando no terminal que se encontra o projeto:

```
yarn 
```

#### Rodando o projeto

Após a instalação de todas as dependências, execute o comando abaixo para rodar o projeto no ambiente de desenvolvimento:

```
yarn dev
```

Para roda no ambiente de produção utilize os comandos:

```
yarn build 
```

Depois:

```
yarn start
```

### Back-end

HTTPS:

```
https://github.com/pedroasdoliveira/petlove-project-backend.git
```

GitHub CLI:

```
gh repo clone pedroasdoliveira/petlove-project-backend
```

#### Instalação

Com o projeto clonado na maquina, execute o comando no terminal que se encontra o projeto:

```
npm install
```

#### Rodando o projeto

Após a instalação de todas as dependências, execute o comando para inicializar o Prisma. Lembrando que para o comando funcionar é necessário todas as configurações do arquivo ".env" estarem configuradas com o banco de dados.

```
npx prisma db push
```

Após o comando ter passado sem nenhum erro, execute o seguinte comando na CLI:

```
npx prisma generate
```

(Para mais detalhes sobre os comandos do Prisma, utilize o comando `npx prisma`)

Após toda a configuração do Prisma, execute o comando a seguir para testar se o projeto está rodando em modo de desenvolvimento.

```
npm run start:dev
```

Para rodar a aplicação no ambiente de produção utilize o comando:

```
npm run build:nest
```

Depois:

```
npm run start:prod
```

#### Rodando a documentação do Compodoc

O Compodoc é um modelo de documentação exclusiva para o Back-end, mostrando sobre todos os componentes da aplicação de forma explicativa.

Para rodar o Compodoc na aplicação é necessário utilizar o comando:

```
npm run compodoc
```

Após isso ele irá gerar um link de acesso.

#### Rodando o Prisma Studio

O Prisma Studio serve como uma tabela em que o usuário pode acessar e modificar diretamente por ele as informações que estão sendo salvas no banco de dados da aplicação.

Para acessa-lo é necessário rodar o comando:

```
npx prisma studio
```

Após o comando você será encaminhado diretamente para a página dele para modificação.
