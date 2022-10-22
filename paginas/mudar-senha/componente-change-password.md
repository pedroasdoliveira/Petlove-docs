---
description: Componente responsável pela redefinição de senha via email.
---

# Componente Change Password

## Introdução

O componente ChangePassword se destina ao controle de restauração de senhas de usuários via email.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Componente Form de restauração de senha.</p></figcaption></figure>

Sua funcionalidade ocorre por meio de um formulário padrão de inscrição de senha para eventual verificação e autorização de acesso.

## Formulário e Validação

Os campos do formulário estão sujeitos a seguinte verificação:

```typescript
interface ChangePasswordData {
  password: string;
  confirmPassword: string;
}
```

A validação dos campos ocorre com a lib "yup" e, à exemplo de sua aplicação, há a seguinte definição:

```typescript
const changePasswordSchema = yup.object().shape({
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
});
```

## Submissão de redefinição de senha:

Através do <mark style="color:purple;">Axios</mark>, <mark style="color:purple;"></mark> tem-se por definição a função de submissão do formulário, listada logo abaixo:

```typescript
const handleChangePassword = (data: ChangePasswordData) => {
    setRequisition(true);
    api
      .patch(`User/change/password/${query?.[0]}/${query?.[1]}`, data)
      .then((response) => {
        setRequisition(false);
        reset();
        toast.success("Senha alterada com sucesso! Faça login para continuar");
        Router.push("/");
      })
      .catch((error) => {
        toast.error("Erro ao alterar senha");
        setRequisition(false);
      });
  };
```

## Componentes Integrados

* React Toast -> Tratamento de respostas
* Yup -> Validação de campos

## Requisitos Funcionais

|                      Descrição                     |                                          Entradas                                          |                                                   Saídas                                                  |                                               Observações ⭐                                               |
| :------------------------------------------------: | :----------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Envio de formulário de redefinição para o servidor | Campos do formulário listados [aqui](componente-change-password.md#formulario-e-validacao) |                                           Restauração de senha.                                           |                                                     ✅                                                     |
|    Acessibilidade via Color Mode - White e Dark    |                    Evento de clique no ícone superior direito \[☀ - 🌙]                    |                       Alteração na visualização de cores dentro de toda a aplicação                       | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|       Tratamento de respostas via ReactToast       |                                              -                                             | <p>SUCCESS: "Senha alterada com sucesso! Faça login para continuar"<br>ERROR: "Erro ao alterar senha"</p> |                                                     ✅                                                     |
|                   Responsividade                   |                                              -                                             |                                                     -                                                     |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\ChangePassword\ChangePassword.tsx
```
