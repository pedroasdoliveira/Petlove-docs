# 🚀 Instalação

## Clonando o projeto

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
