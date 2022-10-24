---
description: >-
  Página responsável pelo sistema de autenticação e registro de usuários dentro
  da aplicação.
---

# Login & Registro🔒

Página `"raiz"` da aplicação para controle de autenticação e segurança.

<figure><img src="../../.gitbook/assets/image (8) (1).png" alt=""><figcaption><p>Página de autenticação/cadastro de usuários</p></figcaption></figure>

Se divide em dois componentes principais:

{% content-ref url="login.md" %}
[login.md](login.md)
{% endcontent-ref %}

{% content-ref url="registro.md" %}
[registro.md](registro.md)
{% endcontent-ref %}

## Requisitos Funcionais

|                   Descrição                  |                       Entradas                       |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------: | :--------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Acessibilidade via Color Mode - White e Dark | Evento de clique no ícone superior direito \[☀ - 🌙] | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                Responsividade                |                           -                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\pages\index.tsx
```
