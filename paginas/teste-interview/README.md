---
description: Página responsável por conduzir o teste "Self Awareness"
---

# Teste - Interview 🧾

## Introdução

A página Interview é o objeto chave de toda a aplicação. Aqui é onde serão avaliados os eixos do profissional em seu teste de autoconhecimento.

Uma vez que seja feita a avaliação, será possível construir o PAD - Plano de Auto Desenvolvimento - do colaborador e, assim, auxiliar em seu processo de evolução de carreira junto ao seu líder imediato.

A página é caracterizada por um layout simples e intuitivo, visando melhorar a experiência do usuário no momento da avaliação, possibilitando uma troca de informações em um meio claro e assertivo.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Página do teste.</p></figcaption></figure>

O usuário conta ainda com mecanismos auxiliares para conduzi-lo em sua avaliação, como uma barra de progresso e subdivisões dos eixos de observação.

Para mais detalhes sobre o teste, consulte [aqui](./#introducao).

## Componentes Integrados

{% content-ref url="stepsform.md" %}
[stepsform.md](stepsform.md)
{% endcontent-ref %}

## Requisitos Funcionais

|                                           Descrição                                           |                                                       Entradas                                                      |                                         Saídas                                         |                                               Observações ⭐                                               |
| :-------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|                          Acessibilidade via Color Mode - White e Dark                         | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> |              Alteração na visualização de cores dentro de toda a aplicação             | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
| Controle de sessão e context <mark style="color:purple;">Auth</mark> com tratamento via Toast |                                                          -                                                          | <p>(Caso não esteja logado): </p><p>ERROR: "Sessão expirada, faça login novamente"</p> |                                                     ✅                                                     |
|                        Barra de progresso para acompanhamento do teste                        |                                                          -                                                          |                                            -                                           |                                                     ✅                                                     |
|                                        Responsividade                                         |                                                          -                                                          |                                            -                                           |                                                     ✅                                                     |

```
Caminho do arquivo: src\pages\Interview
```
