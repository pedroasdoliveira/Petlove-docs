---
description: Componente responsável por efetuar a autenticação de um usuário na aplicação.
---

# Login

## Introdução

O componente de login destina-se a sistematização do controle de autenticação de usuários dentro da aplicação.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Componente de Login</p></figcaption></figure>

O controle é feito através de um formulário com os campos "email" e "senha". Os campos estão devidamente validados e condicionados para melhor experiência do usuário e para o tratamento de possíveis erros no processo de validação.

## Validação dos campos

A validação dos campos ocorre com a lib "yup" e, à exemplo de sua aplicação, há a seguinte definição:

{% code title="Schema de Login" %}
```typescript
const loginSchema = yup.object().shape({
  email: yup
    .string()
    .email("Entre com um email válido")
    .required("Email é obrigatório"),

  password: yup
    .string()
    .min(6, "A senha deve ter no mínimo 6 caracteres")
    .matches(
      /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[$*&@#])[0-9a-zA-Z$*&@#]{6,}$/,
      `Necessário ao menos: 
      1 letra maiúscula, 1 número e 1 caractere especial`
    )
    .required("Senha é obrigatória"),
});
```
{% endcode %}

## Submissão do Form para validação

Através do <mark style="color:purple;">Axios,</mark> tem-se por definição a função de submissão do formulário listada logo abaixo:

{% code title="Função de submissão" %}
```typescript
const handleLogin = (data: LoginData) => {
    api
      .post("/auth", data)
      .then((response) => {
        const headers = {
          headers: {
            Authorization: `Bearer ${response.data.token}`,
          },
        };

        api.get(`User/${data.email}`, headers).then((res) => {
          const user = res.data;
          loginAuth!({ token: response.data.token, user: user });
          Router.push("/Homepage");
        });
      })
      .catch((error) => {
        if (error.response.data.message === "User not verified") {
          toast.error("Usuário não verificado");
        } else {
          toast.error("Email ou senha incorretos");
        }
      });
  };
```
{% endcode %}

Conforme apresentado acima, a função ainda integra tratamento e verificação de respostas para a validação de usuários, além de controle do context <mark style="color:purple;">Auth</mark>.

## Componentes integrados

* React Toast -> Tratamento de respostas
* Yup - Validação de campos

## Requisitos Funcionais

|                    Descrição                   |                         Entradas                        |                              Saídas                             |                                                          Observações ⭐                                                          |
| :--------------------------------------------: | :-----------------------------------------------------: | :-------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
| Login com o servidor da aplicação ( Back-End ) | Email e senha previamente cadastrados no banco de dados |    <p>1° Jwt - (JSON Web Token)<br>2° Usuário autenticado</p>   | O Login somente é válido para usuários previamente verificados via email. A verificação decorre após o [registro](registro.md). |
|  Acessibilidade via Color Mode - White e Dark  |   Evento de clique no ícone superior direito \[☀ - 🌙]  |  Alteração na visualização de cores dentro de toda a aplicação  |            O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>.            |
|     Tratamento de respostas via ReactToast     |                            -                            | ERRORS: "Usuário não verificado" - "Email ou senha incorretos"  |                                                                -                                                                |
|                 Responsividade                 |                            -                            |                                -                                |                                                                ✅                                                                |

```markup
Caminho do arquivo: src\components\Login
```
