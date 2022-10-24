---
description: Componente responsável por listar testes para avaliação do gestor.
---

# User List

## Introdução

O componente UserList é composto de uma tabela responsável por exibir todos os testes feitos por colaboradores para eventual avaliação do gestor.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Componente User List</p></figcaption></figure>

Trata-se, portanto, de um painel de exibição que possibilitará ao gestor um controle maior para suas avaliações.

## Sobre: Mapeamento de dados da tabela

Os dados renderizados na tabela são provisionados pelo context <mark style="color:purple;">users</mark>, responsável por armazenar informações de todos os colaboradores da plataforma.

## Sobre: Avaliação & Confirmação de testes

O gestor, ao avaliar um teste, pode por meio do modal <mark style="color:purple;">ModalLastUserAdm</mark> ter as ferramentas apropriadas para análise e controle de aprovação de testes.

Por meio do modal, é possível dentre outras coisas, refazer o teste junto a um colaborador para confirmação de resultados e calibração para novas funções, por exemplo.

## Componentes Integrados

* ModalLastUserAdm -> controle de avaliação de testes.

## Requisitos Funcionais

|                                                   Descrição                                                   |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :-----------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|                                       Carregamento de dados pelo context                                      |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Integração com <mark style="color:purple;">ModalLastUserAdm</mark> para controle administrador de avaliações. |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
|                                  Acessibilidade via Color Mode - White e Dark                                 | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                                                Responsividade                                                 |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caninho do arquivo: src\components\Lists\UserList\UserList.tsx
```
