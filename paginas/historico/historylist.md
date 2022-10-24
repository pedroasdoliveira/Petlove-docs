---
description: Componente responsável pelo registro dos testes do usuário.
---

# HistoryList

## Introdução

O componente HistoryList é composto de uma tabela responsável pelo registro de testes feitos pelo usuário.

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption><p>Componente HistoryList</p></figcaption></figure>

Sendo exibido como um histórico, essa tabela armazena as seguintes informações:

* Data
* Nível de senioridade
* Detalhes sobre o teste feito (Modal)
* Aprovação

## Sobre: Mapeamento de dados da tabela

Os dados renderizados na tabela tem origem no context <mark style="color:purple;">user</mark>, cujas informações são provisionadas através da API.

## Sobre: Detalhes

O campo de `Detalhes` na tabela corresponde a um botão que chama o modal "<mark style="color:purple;">ModalUser</mark>". Esse modal armazena gráficos comparativos de análises para os testes realizados pelo usuário.

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption><p>ModalUser com gráficos.</p></figcaption></figure>

A comparação é feita sempre entre dois testes: O que foi selecionado na tabela junto ao seu anterior com base na data de execução. É possível visualizar a comparação entre dois tipos de gráficos:

* Radar:

<figure><img src="../../.gitbook/assets/image (17) (1).png" alt=""><figcaption><p>Exemplo de gráfico de radar - ModalUser</p></figcaption></figure>

* Barras:

<figure><img src="../../.gitbook/assets/image (1) (4).png" alt=""><figcaption><p>Exemplo de gráfico de barras - ModalUser</p></figcaption></figure>

PS: No gráfico de Barras, através da lib "Swipper", é possível fazer a transição de um eixo para o outro dentro do próprio modal.

## Componentes Integrados

* ModalUser -> `caminho do arquivo: src\components\ModalUser\ModalUser.tsx`

## Requisitos Funcionais

|                                        Descrição                                       |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|                           Carregamento de dados pelo context                           |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Integração com <mark style="color:purple;">ModalUser</mark> para detalhes sobre testes |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
|                      Acessibilidade via Color Mode - White e Dark                      | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                                     Responsividade                                     |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\Lists\HistoryList\HistoryList.tsx
```
