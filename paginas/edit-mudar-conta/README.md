---
description: Página responsável por alteração de dados do usuário autenticado.
---

# Edit - Mudar conta ⚙

## Introdução

Página responsável pelo controle de informações associadas ao usuário. Através desta página, é possível redefinir a senha de um usuário.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Página Mudar Conta</p></figcaption></figure>

## Componentes Integrados

{% content-ref url="edit-form.md" %}
[edit-form.md](edit-form.md)
{% endcontent-ref %}

## Requisitos Funcionais

|                                           Descrição                                           |                                                       Entradas                                                      |                                         Saídas                                        |                                                          Observações ⭐                                                          |
| :-------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|                          Acessibilidade via Color Mode - White e Dark                         | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> |             Alteração na visualização de cores dentro de toda a aplicação             |            O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>.            |
|                                 Função de Logout da aplicação                                 |             Evento de clique no último ícone do componente <mark style="color:purple;">AsideMenu</mark>             |                    Encerra a sessão do usuário logado na aplicação                    | O encerramento de uma sessão se dá através da exclusão de dados armazenados no <mark style="color:orange;">LocalStorage</mark>. |
| Controle de sessão e context <mark style="color:purple;">Auth</mark> com tratamento via Toast |                                                          -                                                          | <p>(Caso não esteja logado): </p><p>ERROR: "Sessão expirada, faça login novamente</p> |                                                                ✅                                                                |
|                  Navegação entre páginas de usuário no menu lateral esquerdo                  |                    Links de páginas de navegação: Profile, Histórico, Especialidades, Mudar Conta                   |                          Retorna página selecionada no menu.                          |                                                                -                                                                |
|                                        Responsividade                                         |                                                          -                                                          |                                           -                                           |                                                                ✅                                                                |

```
Caminho do arquivo: src\pages\Edit
```
