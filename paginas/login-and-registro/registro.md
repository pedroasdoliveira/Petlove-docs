---
description: Componente responsável pelo cadastro de novos usuários na plataforma.
---

# Registro

## Introdução

O componente de registro destina-se ao controle de cadastro de colaboradores e demais usuários dentro da aplicação.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Componente de registro</p></figcaption></figure>

Sua funcionalidade ocorre por meio de um formulário padrão de inscrição para eventual verificação e autorização de acesso.

## Formulário e Validação

Os campos do formulário estão sujeitos a seguinte configuração:

{% code title="Type Register" %}
```tsx
interface RegisterData {
  email: string;
  name: string;
  password: string;
  confirmPassword: string;
  terms: boolean;
}
```
{% endcode %}

A validação dos campos ocorre com a lib "yup" e, à exemplo de sua aplicação, há a seguinte definição:

{% code title="Schema Register" %}
```tsx
const registerSchema = yup.object().shape({
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

  confirmPassword: yup
    .string()
    .oneOf([yup.ref("password"), null], "Senhas não conferem")
    .required("Confirmação de senha é obrigatória"),

  name: yup
    .string()
    .min(3, "Nome deve ter no mínimo 3 caracteres")
    .max(40, "Nome deve ter no máximo 40 caracteres")
    .required("Nome é obrigatório"),

  terms: yup.boolean().oneOf([true]),
});
```
{% endcode %}

## Submissão de Form de Registro

Através do <mark style="color:purple;">Axios</mark>, <mark style="color:purple;"></mark> tem-se por definição a função de submissão do formulário, listada logo abaixo:

{% code title="Submit Register" %}
```tsx
const handleRegister = (data: RegisterData) => {
    api.post("/User/create", data).then((response) => {
      console.log(response);
      toast.success("Perfil registrado com sucesso!");
      setTabIndex(0);
    });
  };
```
{% endcode %}

## Componentes Integrados

* React Toast -> Tratamento de respostas
* Yup -> Validação de campos

## Requisitos Funcionais

|                    Descrição                    |                                 Entradas                                 |                             Saídas                            |                                               Observações ⭐                                               |
| :---------------------------------------------: | :----------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Envio de formulário de registro para o servidor | Campos do formulário listados [aqui](registro.md#formulario-e-validacao) | Criação de usuário & envio de email para verificação de conta |                                                     -                                                     |
|   Acessibilidade via Color Mode - White e Dark  |           Evento de clique no ícone superior direito \[☀ - 🌙]           | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|      Tratamento de respostas via ReactToast     |                                     -                                    |                               -                               |                                                     ✅                                                     |
|                 Responsividade                  |                                     -                                    |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\RegisterComponent\RegisterComponent.tsx
```
