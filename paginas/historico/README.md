---
description: Página de visualização de evolução do usuário com os testes na plataforma.
---

# Histórico ⏳

## Introdução

A página de Histórico é responsável por simular a grade evolutiva de um colaborador através dos testes realizados pelo mesmo.

<figure><img src="../../.gitbook/assets/image (5) (3).png" alt=""><figcaption><p>Página de Histórico</p></figcaption></figure>

A funcionalidade dessa página está vinculada ao registro de avaliações de testes e análises comparativas entre gráficos voltados a avaliação de soft e hard skills do usuário.

## Componentes Integrados

{% content-ref url="areacomposedchart.md" %}
[areacomposedchart.md](areacomposedchart.md)
{% endcontent-ref %}

{% content-ref url="historylist.md" %}
[historylist.md](historylist.md)
{% endcontent-ref %}

{% content-ref url="graficos-de-evolucao.md" %}
[graficos-de-evolucao.md](graficos-de-evolucao.md)
{% endcontent-ref %}

## Requisitos Funcionais

|                                           Descrição                                           |                                                       Entradas                                                      |                                         Saídas                                         |                                                          Observações ⭐                                                          |
| :-------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|                          Acessibilidade via Color Mode - White e Dark                         | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> |              Alteração na visualização de cores dentro de toda a aplicação             |            O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>.            |
|                                 Função de Logout da aplicação                                 |             Evento de clique no último ícone do componente <mark style="color:purple;">AsideMenu</mark>             |                     Encerra a sessão do usuário logado na aplicação                    | O encerramento de uma sessão se dá através da exclusão de dados armazenados no <mark style="color:orange;">LocalStorage</mark>. |
| Controle de sessão e context <mark style="color:purple;">Auth</mark> com tratamento via Toast |                                                          -                                                          | <p>(Caso não esteja logado): </p><p>ERROR: "Sessão expirada, faça login novamente"</p> |                                                                ✅                                                                |
|                  Navegação entre páginas de usuário no menu lateral esquerdo                  |       Links de páginas de navegação: Profile, Histórico, Especialidades, Mudar Conta, Histórico, Administração      |                           Retorna página selecionada no menu.                          |                                                                -                                                                |
|                                        Responsividade                                         |                                                          -                                                          |                                            -                                           |                                                                ✅                                                                |

```
Caminho do arquivo: src\pages\History
```
