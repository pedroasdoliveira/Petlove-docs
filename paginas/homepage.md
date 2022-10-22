---
description: Página inicial após o login.
---

# Homepage 🏡

## Introdução

Página `home` responsável por direcionar usuário para [Perfil](perfil.md) e para de realização do [Teste](teste-interview/).

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

## Componentes Integrados

* Aside Menu -> `Caminho do arquivo: src\components\AsideMenu\AsideMenu.tsx`

## Requisitos Funcionais



|                                           Descrição                                           |                                                                    Entradas                                                                    |                                         Saídas                                         |                                                          Observações ⭐                                                          |
| :-------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|                          Acessibilidade via Color Mode - White e Dark                         |               <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p>              |              Alteração na visualização de cores dentro de toda a aplicação             |            O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>.            |
|                                 Função de Logout da aplicação                                 |                           Evento de clique no último ícone do componente <mark style="color:purple;">AsideMenu</mark>                          |                     Encerra a sessão do usuário logado na aplicação                    | O encerramento de uma sessão se dá através da exclusão de dados armazenados no <mark style="color:orange;">LocalStorage</mark>. |
| Controle de sessão e context <mark style="color:purple;">Auth</mark> com tratamento via Toast |                                                                        -                                                                       | <p>(Caso não esteja logado): </p><p>ERROR: "Sessão expirada, faça login novamente"</p> |                                                                ✅                                                                |
|                               Navegação para [Perfil](perfil.md)                              | <p>Evento de clique no segundo ícone do componente <mark style="color:purple;">AsideMenu</mark><br><mark style="color:purple;"></mark>[🏠]</p> |                           Redireciona para a página destacada                          |                                                                -                                                                |
|                                        Responsividade                                         |                                                                        -                                                                       |                                            -                                           |                                                                ✅                                                                |

```
Caminho do arquivo: src\pages\Homepage
```
