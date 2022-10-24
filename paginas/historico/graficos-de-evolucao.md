---
description: >-
  Seção responsável por exibir graficamente a evolução do usuário por meio dos
  testes
---

# Gráficos de Evolução

## Introdução

Seção final da página de Histórico. Utilizada para mostrar, por meio de gráficos, a evolução de um colaborador dentro da plataforma.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Seção Histórico de evolução em gráfico - Página Histórico</p></figcaption></figure>

## Gráficos disponíveis

Com o <mark style="color:purple;">Recharts</mark> é possível a visualização de informações por meio das seguintes variações de gráficos:

* Radar - Todos os testes

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

* Linha - Todos os testes - Pessoas

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* Linha - Todos os testes - Processos

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Linha - Todos os testes - Influência

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* Linha - Todos os testes - Sistemas

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* Linha - Todos os testes - Tecnologia

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

## Componentes Integrados

* Swipper -> Transição de gráficos de comparação.
* Recharts -> Gráficos

## Requisitos Funcionais

|                   Descrição                  |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|      Carregamento de dados pelo context      |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
|   Transição de gráficos através do Swipper   |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Acessibilidade via Color Mode - White e Dark | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                Responsividade                |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\pages\History
```
