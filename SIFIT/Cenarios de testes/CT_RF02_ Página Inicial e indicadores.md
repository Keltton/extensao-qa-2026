## Cenário 02: Página Inicial e indicadores.

### Caso de Teste 01: Exibição dos indicadores após o login.

| ID       | Descrição |
| :------- | :-------- |
| C02-CT01 | A Página Inicial deve exibir os cards de resumo da academia. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário fez login |
| **QUANDO** a Página Inicial for carregada |
| **ENTÃO** devem ser exibidos os cards de Clientes Ativos, Ausentes, Matrículas, Personais e o filtro de período do mês atual |

| **Critérios de aceitação** |
| :------------------------- |
| Cards exibidos com o período 01 a 31 do mês corrente. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Cards exibidos; período padrão 01/10/2026 a 31/10/2026. | [Print](../Evidencias/C02-CT01.png) | - |

---

### Caso de Teste 02: Card "em aberto" reflete contas pendentes.

| ID       | Descrição |
| :------- | :-------- |
| C02-CT02 | O valor em aberto deve somar as contas a receber pendentes. |

| **Pré-condições** |
| :---------------- |
| Existir conta a receber pendente no período. |

| **Passos** |
| :--------- |
| **DADO** que existe uma conta pendente com vencimento no mês |
| **QUANDO** o usuário acessar a Página Inicial |
| **ENTÃO** o card "em aberto" deve exibir a quantidade total pendente|

| **Critérios de aceitação** |
| :------------------------- |
| Valor em aberto coerente com Contas a Receber. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | O card exibe "R$ 0,00 em aberto". | [Vídeo Jam](https://jam.dev/c/a6cc5c0a-010c-4f85-8aa3-762e5c4ec3a0) | BUG-003 |

---

### Caso de Teste 03: Filtro de período com data inicial maior que a final.

| ID       | Descrição |
| :------- | :-------- |
| C02-CT03 | O sistema deve impedir ou alertar sobre um período inválido. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está na Página Inicial |
| **E** seleciona 31/10/2026 como data inicial |
| **QUANDO** selecionar 01/10/2026 como data final |
| **ENTÃO** o sistema deve bloquear a seleção ou exibir aviso de período inválido |

| **Critérios de aceitação** |
| :------------------------- |
| Período invertido não deve ser aceito. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Período 31/10 a 01/10 aceito sem aviso; cards seguem exibindo dados (ex.: 2 matrículas no período). | [Vídeo Jam](https://jam.dev/c/5f7f9e52-3989-42d5-99c2-66b747dec9e3) | BUG-004 |

---
