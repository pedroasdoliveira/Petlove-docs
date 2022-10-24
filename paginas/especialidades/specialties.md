---
description: Componente responsável por renderizar as informações de especialidades.
---

# Specialties

## Introdução

O componente Specialties está encarregado de exibir as informações de especialidades (níveis de senioridade).

Para tal, as informações são obtidas através da API e armazenadas no context <mark style="color:purple;">Specialtys</mark> (`src\contexts\specialtys.tsx`).



## Context Specialtys

```typescript
export const SpecialtysContextProvider = ({ children }: SpecialtysContextProps) => {
  const [specialtys, setSpecialtys] = useState<any[]>([]);

  const { logged } = useAuth();

  const handleGetSpecialtys = () => {
    let token: any;

    if (typeof window !== "undefined") {
      token = localStorage.getItem("token") || "";
    }

    const headers = {
      headers: {
        Authorization: `Bearer ${token}`,
      },
    };

      api.get(`/Specialty`, headers).then((res) => setSpecialtys(res.data)).catch((err) => console.log(err));
  };

  useEffect(() => {
    if (logged) handleGetSpecialtys();
  }, [logged]);
```

## Especialidades:

<figure><img src="../../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>Especialidades Trainee e Júnior</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>Especialidades Pleno + Senior</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

## Requisitos Funcionais

|                         Descrição                        |                       Entradas                       |                             Saídas                            |                                               Observações ⭐                                               |
| :------------------------------------------------------: | :--------------------------------------------------: | :-----------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Carregamento de informações da página através do context |                           -                          |                               -                               |                                                     ✅                                                     |
|       Acessibilidade via Color Mode - White e Dark       | Evento de clique no ícone superior direito \[☀ - 🌙] | Alteração na visualização de cores dentro de toda a aplicação | O controle do modo de cores ocorre através do context <mark style="color:purple;">ToggleModeStyle</mark>. |
|                      Responsividade                      |                           -                          |                               -                               |                                                     ✅                                                     |

```
Caminho do arquivo: src\components\Specialties\Specialties.tsx
```
