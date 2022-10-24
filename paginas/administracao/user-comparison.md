---
description: >-
  Componente destinado a visualização de comparações entre entidades da
  aplicação.
---

# User Comparison

## Introdução

O componente UserComparison destina-se ao controle de comparações e análises de usuários colaboradores dentro da aplicação.

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Divide-se em seções principais:

* Ranking de Usuários
* Ranking de Equipes
* Comparações entre gráficos.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

## Componentes Integrados

* Swiper -> Transição de gráficos.

## Requisitos Funcionais

|                   Descrição                  |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|      Carregamento de dados pelo context      |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
|                    Swiper                    |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Acessibilidade via Color Mode - White e Dark | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                Responsividade                |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\Lists\UserComparisons\UserComparisons.tsx
```
