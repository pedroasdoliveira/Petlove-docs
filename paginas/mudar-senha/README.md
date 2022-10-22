---
description: Página responsável pela redefinição de senha
---

# Mudar Senha ❗

## Introdução

Página de restauração de senha.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Página de alteração de senha.</p></figcaption></figure>

Por meio dessa página será permitido ao usuário redefinir sua senha após recebimento do email com o link para a restauração.

## Componentes Integrados

{% content-ref url="componente-change-password.md" %}
[componente-change-password.md](componente-change-password.md)
{% endcontent-ref %}

## Requisitos Funcionais

|                   Descrição                  |                       Entradas                       |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------: | :--------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Acessibilidade via Color Mode - White e Dark | Evento de clique no ícone superior direito \[☀ - 🌙] | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                Responsividade                |                           -                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\pages\Change
```
