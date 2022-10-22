---
description: Página inicial com informações do usuário logado.
---

# Perfil 🙎🏽‍♂️

## Introdução

A página Profile é o próximo destino do usuário após realizar o teste "Self Awareness".

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Página Profile</p></figcaption></figure>

Aqui ficarão contidas as informações de estado de avaliação do último teste feito pelo usuário, além de dados relativos a conta como nome, foto, endereço eletrônico, função, etc.

O estado de avaliação do teste pode ser visto aqui:

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption><p>Componentes dinâmicos da página profile</p></figcaption></figure>

O gráfico apresentado acima indica o progresso da avaliação pelo gestor. Possui três estados principais:

* Aguardando 🟡 -> representado pela cor amarela, mostra que o teste ainda se encontra em avaliação pelo gestor.
* Reprovado 🔴 -> representado pela cor vermelha, entende-se que o usuário não obteve aprovação para o teste realizado.
* Aprovado 🟢 -> representado pela cor verde, reflete a aprovação do teste feito pelo usuário

O quadro de informações à direita mantém dados do usuário que são atualizados conforme a progressão de avaliação do teste.

## Requisitos Funcionais

|                                           Descrição                                           |                                                       Entradas                                                      |                                         Saídas                                         |                                                          Observações ⭐                                                          |
| :-------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|                          Acessibilidade via Color Mode - White e Dark                         | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> |              Alteração na visualização de cores dentro de toda a aplicação             |            O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>.            |
|                                 Função de Logout da aplicação                                 |             Evento de clique no último ícone do componente <mark style="color:purple;">AsideMenu</mark>             |                     Encerra a sessão do usuário logado na aplicação                    | O encerramento de uma sessão se dá através da exclusão de dados armazenados no <mark style="color:orange;">LocalStorage</mark>. |
| Controle de sessão e context <mark style="color:purple;">Auth</mark> com tratamento via Toast |                                                          -                                                          | <p>(Caso não esteja logado): </p><p>ERROR: "Sessão expirada, faça login novamente"</p> |                                                                ✅                                                                |
|                  Navegação entre páginas de usuário no menu lateral esquerdo                  |       Links de páginas de navegação: Profile, Histórico, Especialidades, Mudar Conta, Histórico, Administração      |                           Retorna página selecionada no menu.                          |                                                                -                                                                |
|                                        Responsividade                                         |                                                          -                                                          |                                            -                                           |                                                                ✅                                                                |

```
Caminho do arquivo: src\pages\Profile
```
