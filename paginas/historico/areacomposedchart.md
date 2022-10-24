---
description: >-
  Componente com gráfico integrado que remonta o histórico de progressão de
  funções do usuário.
---

# AreaComposedChart

## Introdução

O componente AreaComposedChart é responsável por exibir graficamente o histórico de evolução do usuário, detalhando sua progressão de carreira em suas funções após realização do teste "Self Awareness"

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Componente Gráfico: AreaComposedChart</p></figcaption></figure>

A exibição de conteúdo ocorre por meio dos contexts <mark style="color:purple;">user</mark> e <mark style="color:purple;">specialtys</mark>.

## Sobre: Mapeamento de dados para o gráfico

```typescript
const mountUserData = () => {
    const data = user.results?.sort((a: any, b: any) => {
      return Number(a.createdAt) - Number(b.createdAt);
    });

    const dataToChart = data?.map((item: any) => {

      return {
        nextRole: item.nextRole,
        createdAt: `${new Date(item.createdAt).toLocaleDateString()}`,
        allSpecialities: [...speciality!],
      }
    });

    return dataToChart;
};
```

## Componentes Integrados

* Recharts -> Gráfico de linha/área do histórico de funções.

## Requisitos Funcionais

|                   Descrição                  |                                                       Entradas                                                      |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|     Carregamento de dados pelos contexts     |                                                          -                                                          |                               -                               |                                                     ✅                                                     |
| Acessibilidade via Color Mode - White e Dark | <p>Evento de clique no primeiro ícone do componente <mark style="color:purple;">AsideMenu</mark></p><p>[☀ - 🌙]</p> | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                Responsividade                |                                                          -                                                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\Graphics\AreaComposedChart.tsx
```
