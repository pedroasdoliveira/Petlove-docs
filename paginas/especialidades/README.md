---
description: Página de descrição de níveis de especialidade.
---

# Especialidades 👑

## Introdução

A página de Especialidades contém a descrição de competências necessárias para ocupação de funções relacionadas às senioridades avaliadas no teste.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Página de Especialidades.</p></figcaption></figure>

## Componentes Integrados

{% content-ref url="specialties.md" %}
[specialties.md](specialties.md)
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
Caminho do arquivo: src\pages\Specialty
```
