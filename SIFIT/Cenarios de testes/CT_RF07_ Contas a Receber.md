## Cenário 07: Contas a Receber.

### Caso de Teste 01: Conta gerada pela matrícula (busca por nome).

| ID       | Descrição |
| :------- | :-------- |
| C07-CT01 | A matrícula deve gerar a parcela em Contas a Receber. |

| **Pré-condições** |
| :---------------- |
| Matrícula de teste cadastrada (C06-CT02). |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Contas a Receber |
| **E** digita o nome do cliente de teste no filtro Nome |
| **QUANDO** clicar em "Buscar" |
| **ENTÃO** deve ser listada a parcela da matrícula como PENDENTE |

| **Critérios de aceitação** |
| :------------------------- |
| Parcela listada com valor e status corretos. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Parcela listada com o valor do plano e status PENDENTE. | [Vídeo Jam](https://jam.dev/c/c6513540-0180-4ee7-a5a2-7e1043a24c42) | - |

---

### Caso de Teste 02: Listagem do período sem filtro de nome.

| ID       | Descrição |
| :------- | :-------- |
| C07-CT02 | Sem filtro de nome, a listagem deve exibir todas as contas do período. |

| **Pré-condições** |
| :---------------- |
| Conta com vencimento em outubro/2026. |

| **Passos** |
| :--------- |
| **DADO** que o filtro está em Tipo de Data "Vencimento", 01/10/2026 a 31/10/2026 e Status "Todos" |
| **E** o filtro Nome está vazio |
| **QUANDO** clicar em "Buscar" |
| **ENTÃO** as contas devem aparecer na lista |

| **Critérios de aceitação** |
| :------------------------- |
| Todas as contas do período listadas. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Lista todas as contas do período. | [Vídeo Jam](https://jam.dev/c/40bd8eea-2b6b-4941-adcd-c7a0fd3c3074) | - |

---

### Caso de Teste 03: Filtro por status Pendente.

| ID       | Descrição |
| :------- | :-------- |
| C07-CT03 | O filtro deve listar as contas pendentes do período. |

| **Pré-condições** |
| :---------------- |
| Contas PENDENTES em outubro/2026. |

| **Passos** |
| :--------- |
| **DADO** que o período é 01/10/2026 a 31/10/2026 |
| **E** o usuário seleciona Status "Pendente" |
| **QUANDO** clicar em "Buscar" |
| **ENTÃO** as contas pendentes devem ser listadas |

| **Critérios de aceitação** |
| :------------------------- |
| Contas pendentes listadas. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Lista traz as contas pendentes do período. | [Vídeo Jam](https://jam.dev/c/b54c7e5e-b11a-4612-afdd-2db006bf602d) | - |

---

### Caso de Teste 04: Cards de resumo consideram contas pendentes.

| ID       | Descrição |
| :------- | :-------- |
| C07-CT04 | "Previsto para o Mês" e "Pendentes no Mês" devem incluir as contas pendentes. |

| **Pré-condições** |
| :---------------- |
| Contas PENDENTES no mês filtrado. |

| **Passos** |
| :--------- |
| **DADO** que existe mais de uma conta pendente no mês |
| **QUANDO** o usuário acessar Contas a Receber |
| **ENTÃO** "Pendentes no Mês" deve ser ≥ 1 e "Previsto para o Mês" deve incluir o valor pendente no mês filtrado |

| **Critérios de aceitação** |
| :------------------------- |
| Cards coerentes com as contas existentes. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Os cards "Pendentes no Mês" e "Previsto para o Mês" não refletem as contas pendentes do mês filtrado. | [Vídeo Jam](https://jam.dev/c/d2060185-943a-429b-bb7f-786c1bcd6119) | BUG-014 |

---
