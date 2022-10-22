---
description: Componente responsável por alterar informações e preferências do usuário.
---

# Edit Form

## Introdução

O componente de <mark style="color:purple;">EditForm</mark> é responsável pela redefinição de dados e configurações do usuário associado a conta.



<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p>Componente de EditForm</p></figcaption></figure>

Modificações feitas são realizadas através de múltiplos formulários de edição.

## Formulário e Validação de Senhas

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

## Form: Notificações de Email

O controle de preferência de recebimento de notificações via email ocorre por meio de um hook:

```tsx
const [emailNotification, setEmailNotification] = useState("");
```

Seleção de configuração:

```tsx
<RadioGroup
  onChange={setEmailNotification}
  value={emailNotification}
>
  <Stack>
    <Radio value="all">Todos</Radio>
    <Radio value="team">Somente do meu time</Radio>
    <Radio value="none">Nenhum</Radio>
  </Stack>
</RadioGroup>
```

## Form: Imagem de perfil:

```typescript
const file = e.target.files?.[0];
//verifica se o file não é imagem
if (!file?.type.match(/image.*/)) {
  toast.error("Arquivo não é uma imagem");
  return;
}

//verifica se o tamanho do arquivo é maior que 5mb
if (file.size > 5 * 1024 * 1024) {
  toast.error("Arquivo muito grande");
  return;
}

if (file) {
  setLoading(true);
  const formData = new FormData();
  formData.append("image", file);
  formData.append("album", process.env.NEXT_PUBLIC_CLIENT_ALBUM as string);

  axios
    .post("https://api.imgur.com/3/image", formData, {
      headers: {
        Authorization: process.env.NEXT_PUBLIC_CLIENT_ID as string,
      },
    })
    .then((response) => {
      setImage(response.data.data.link);
      setLoading(false);
    })
    .catch((error) => {
      toast.error("Erro ao enviar imagem");
      setLoading(false);
    });
}
}}
```

## Submit Form de Redefinição de Informações

Através do <mark style="color:purple;">Axios</mark>, <mark style="color:purple;"></mark> tem-se por definição a função de submissão do formulário, listada logo abaixo:

```typescript
const handleEdit = (data: EditData) => {
    setRequisition(true);
    const token = localStorage.getItem("token");

    const headers = {
      headers: {
        Authorization: `Bearer ${token}`,
      },
    };

    if (!data.newPassword) {
      delete data.newPassword;
      delete data.confirmPassword;
    }

    const dataToSend = {
      ...data,
      emailNotification,
      profilePicture: image,
    };

    api
      .patch(`/User/${user.email}`, dataToSend, headers)
      .then((response) => {
        toast.success("Dados alterados com sucesso!");
        handleGetUsers();
        setRequisition(false);
        reset();
      })
      .catch((error) => {
        toast.error("Erro ao alterar dados!");
        console.log(error);
        console.log(dataToSend);
        setRequisition(false);
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
