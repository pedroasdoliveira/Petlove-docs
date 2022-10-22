---
description: >-
  Página responsável pelo sistema de redefinição de senha em caso de
  desconhecimento.
---

# Esqueci a Senha

## Introdução

Página para redefinição de senha por email.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Página de redefinição de senha via email</p></figcaption></figure>

Sua funcionalidade ocorre através de um formulário com o campo "email". Uma vez enviada a solicitação, o usuário receberá uma notificação com o link para redefinição de senha. O link remete a página <mark style="color:purple;">Change</mark>.

## Formulário e Validação

O campo "email" está sujeito a seguinte configuração:

```typescript
interface ForgotPasswordData {
  email: string;
}
```

A validação dos campos ocorre com a lib "yup" e, à exemplo de sua aplicação, há a seguinte definição:

```typescript
const forgotPasswordSchema = yup.object().shape({
  email: yup
    .string()
    .email("Entre com um email válido")
    .required("Email é obrigatório"),
});
```

## Submit para envio de redefinição de senha

Através do <mark style="color:purple;">Axios</mark>, <mark style="color:purple;"></mark> tem-se por definição a função de submissão do formulário, listada logo abaixo:

```typescript
const handleForgotPassword = (data: ForgotPasswordData) => {
    setRequisition(true);
    api
      .get(`User/send/${data.email}`)
      .then((response) => {
        setRequisition(false);
        reset();
        toast.success(
          "Email para redefinição de senha enviado com sucesso! Verifique sua caixa de entrada."
        );
        Router.push("/");
      })
      .catch((error) => {
        toast.error("Erro ao enviar email para redefinição de senha!");
        setRequisition(false);
      });
  };
```

## Componentes Integrados

* React Toast -> Tratamento de respostas
* Yup -> Validação de campos

## Requisitos Funcionais

|                   Descrição                  |                                     Entradas                                    |                                                                               Saídas                                                                               |                                               Observações ⭐                                               |
| :------------------------------------------: | :-----------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Envio de formulário de email para o servidor | Campos do formulário listados [aqui](esqueci-a-senha.md#formulario-e-validacao) |                                                              Envio de email para redefinição de senha                                                              |                                                     ✅                                                     |
| Acessibilidade via Color Mode - White e Dark |               Evento de clique no ícone superior direito \[☀ - 🌙]              |                                                    Alteração na visualização de cores dentro de toda a aplicação                                                   | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|    Tratamento de respostas via ReactToast    |                                        -                                        | <p>SUCCESS: "Email para redefinição de senha enviado com sucesso! Verifique sua caixa de entrada."<br>ERROR: "Erro ao enviar email para redefinição de senha!"</p> |                                                     ✅                                                     |
|                Responsividade                |                                        -                                        |                                                                                  -                                                                                 |                                                     ✅                                                     |

```
Caminho do arquivo: src\pages\index.tsx
```
