---
description: Componente de exibição de usuários colaboradores na plataforma
---

# All User List

## Introdução

O componente <mark style="color:purple;">AllUserList</mark> se destina a visualização e controle de usuários da plataforma.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Componente AllUserList</p></figcaption></figure>

É composto por uma tabela cujos dados são provisionados pela API e armazenados no context <mark style="color:purple;">users</mark>.

Inclui-se também os mecanismos de busca e de filtragem de usuários para maior usabilidade da aplicação.

## Sobre: Mapeamento de dados da tabela

Os dados renderizados na tabela têm origem no context <mark style="color:purple;">users</mark>, onde são armazenadas todas as informações de todos os usuários da plataforma.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## Sobre: Mecanismo de busca e filtro

O componente ainda integra uma barra de busca e filtros para melhorar a localização e o acesso a usuários dentro da plataforma.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Mecanismo de busca</p></figcaption></figure>

É composto, portanto, de uma barra de pesquisa, por onde é possível localizar os usuários pelos seguintes adereços:

* Nome
* Email
* Cargo
* Chapter
* Equipe

E também, é possível aprimorar a precisão dos resultados com o botão Filter, por onde ocorre a filtragem das informações com os mesmos adereços citados acima.

## Sobre: Atualização de dados e Controle

É permitido ao administrador fazer atualizações e alterações de dados de usuários da plataforma. Atrela-se o funcionamento dessa funcionalidade ao modal <mark style="color:purple;">ModalUserAdm</mark> por onde são empregadas as configurações de edição.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>ModalUserAdm - Overview</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>ModalUserAdm - Edit</p></figcaption></figure>

Também é possível a visualização de informações relativas ao usuário selecionado, assim como comparações disponíveis através de gráficos.

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## Componentes Integrados

* ModalUserAdm -> controle de administração para usuários.

## Requisitos Funcionais

|                                                Descrição                                               |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :----------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|                                   Carregamento de dados pelo context                                   |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Integração com <mark style="color:purple;">ModalUserAdm</mark> para controle administrador de usuários |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
|                              Acessibilidade via Color Mode - White e Dark                              | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                                             Responsividade                                             |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\AllUserList\AllUserList.tsx
```
