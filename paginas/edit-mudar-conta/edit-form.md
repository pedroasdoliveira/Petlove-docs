---
description: Componente responsável por alterar informações do usuário.
---

# Edit Form

## Introdução

O componente de <mark style="color:purple;">EditForm</mark> é responsável pela redefinição de senhas de usuários dentro da aplicação.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Componente de EditForm</p></figcaption></figure>

A restauração de senhas é feita através de um formulário padrão.

## Formulário e Validação

Os campos do formulário estão sujeitos a seguinte configuração:

{% code title="Type do Form" %}
```typescript
interface EditData {
  password: string;
  newPassword?: string;
  confirmPassword?: string;
}
```
{% endcode %}

A validação dos campos ocorre com a lib "yup" e, à exemplo de sua aplicação, há a seguinte definição:

{% code title="Schema Edit" %}
```typescript
const editSchema = yup.object().shape(
  {
    password: yup
      .string()
      .min(6, "A senha deve ter no mínimo 6 caracteres")
      .matches(
        /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[$*&@#])[0-9a-zA-Z$*&@#]{6,}$/,
        `Necessário ao menos: 
    1 letra maiúscula, 1 número e 1 caractere especial`
      )
      .required("Senha é obrigatória"),

    newPassword: yup
      .string()
      .required("Nova senha é obrigatória")
      .when("newPassword", {
        is: (val: string) => (val ? true : false),
        then: yup
          .string()
          .min(6, "A senha deve ter no mínimo 6 caracteres")
          .matches(
            /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[$*&@#])[0-9a-zA-Z$*&@#]{6,}$/,
            `Necessário ao menos:
        1 letra maiúscula, 1 número e 1 caractere especial`
          ),
      }),

    confirmPassword: yup
      .string()
      .required("Confirmar a nova senha é obrigatório")
      .when("confirmPassword", {
        is: (val: string) => (val ? true : false),
        then: yup
          .string()
          .oneOf([yup.ref("newPassword"), null], "Senhas não conferem"),
      }),
  },
  [
    ["newPassword", "newPassword"],
    ["confirmPassword", "confirmPassword"],
  ]
);
```
{% endcode %}

## Submissão do Form de Redefinição de Senha

Através do <mark style="color:purple;">Axios</mark>, <mark style="color:purple;"></mark> tem-se por definição a função de submissão do formulário, listada logo abaixo:

```typescript
const handleEdit = (data: EditData) => {
    const token = localStorage.getItem("token");

    const headers = {
      headers: {
        Authorization: `Bearer ${token}`,
      },
    };

    api
      .patch(`/User/${user.email}`, data, headers)
      .then((response) => {
        toast.success("Dados alterados com sucesso!");
        handleGetUsers();
      })
      .catch((error) => {
        toast.error("Erro ao alterar dados!");
      });
  };
```

## Componentes integrados

* React Toast -> Tratamento de respostas
* Yup -> Validação de campos

## Requisitos Funcionais

|                      Descrição                     |                                                       Entradas                                                      |                                      Saídas                                      |                                               Observações ⭐                                               |
| :------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Envio de formulário com alterações para o servidor |                      Campos do formulário listados [aqui](edit-form.md#formulario-e-validacao)                      |        Redefinição de senha, caso informações fornecidas estejam corretas        |                                                     -                                                     |
|    Acessibilidade via Color Mode - White e Dark    | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> |           Alteração na visualização de cores dentro de toda a aplicação          | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|       Tratamento de respostas via ReactToast       |                                                          -                                                          | <p>ERROR: "Erro ao alterar dados"<br>SUCCESS: "Dados alterados com Sucesso!"</p> |                                                     ✅                                                     |
|                   Responsividade                   |                                                          -                                                          |                                         -                                        |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\EditForm\EditForm.tsx
```
