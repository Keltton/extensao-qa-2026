## Cenário 06: Matrículas.

### Caso de Teste 01: Salvar matrícula sem cliente.

| ID       | Descrição |
| :------- | :-------- |
| C06-CT01 | O cliente é obrigatório na matrícula. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Matrículas > "Cadastrar Matrícula" |
| **QUANDO** clicar em "Salvar" sem selecionar cliente |
| **ENTÃO** deve ser exibido aviso de cliente obrigatório |

| **Critérios de aceitação** |
| :------------------------- |
| Cadastro bloqueado com aviso. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Exibido o aviso "Selecione o cliente!". | [Print](../Evidencias/C06-CT01.png) | - |

---

### Caso de Teste 02: Cadastrar matrícula válida.

| ID       | Descrição |
| :------- | :-------- |
| C06-CT02 | A matrícula deve ser criada e gerar a conta a receber. |

| **Pré-condições** |
| :---------------- |
| Cliente e plano cadastrados. |

| **Passos** |
| :--------- |
| **DADO** que o usuário seleciona o cliente pela lupa |
| **E** seleciona a Modalidade (plano de teste criado em C05-CT04), Tipo Pagamento "Dinheiro", Dia Vencimento 10 e "Pag. Via Sistema" = Não |
| **E** clica em "Salvar" e "Escolher" (1 parcela) |
| **QUANDO** responder "Cancelar" para pagar agora e "Cancelar" para a anamnese |
| **ENTÃO** a matrícula deve aparecer como ATIVA na listagem |

| **Critérios de aceitação** |
| :------------------------- |
| Matrícula listada e contador de ativas atualizado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Matrícula ATIVA; conta gerada (ver C07-CT01). | [Vídeo Jam](https://jam.dev/c/000c4da1-d2e3-426d-af91-db39a4553bac) | - |

---

### Caso de Teste 03: Data da parcela aceita data inválida.

| ID       | Descrição |
| :------- | :-------- |
| C06-CT03 | O campo Data do modal "Quantidade Parcelas" deve aceitar somente datas válidas. |

| **Pré-condições** |
| :---------------- |
| Formulário de matrícula preenchido (C06-CT02). |

| **Passos** |
| :--------- |
| **DADO** que o usuário clicou em "Salvar" na matrícula |
| **QUANDO** o modal "Quantidade Parcelas" for exibido |
| **E** informar uma data inválida no campo Data |
| **ENTÃO** o sistema deve rejeitar a data inválida |

| **Critérios de aceitação** |
| :------------------------- |
| Somente datas válidas no padrão DD/MM/AAAA são aceitas. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | O sistema aceita a data inválida "2026/05/192". | [Vídeo Jam](https://jam.dev/c/02ee32cf-7b68-4011-9cd9-d0faaba8470e) | BUG-012 |

---

### Caso de Teste 04: Matrícula oferece apenas planos ativos.

| ID       | Descrição |
| :------- | :-------- |
| C06-CT04 | Planos inativos não devem estar disponíveis para nova matrícula. |

| **Pré-condições** |
| :---------------- |
| Existirem planos inativos. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está em "Cadastrar Matrícula" |
| **QUANDO** abrir o campo Modalidade |
| **ENTÃO** apenas planos ativos devem ser listados |

| **Critérios de aceitação** |
| :------------------------- |
| Planos inativos ausentes da lista. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Planos com status INATIVO aparecem na lista e podem ser selecionados. | [Vídeo Jam](https://jam.dev/c/867affda-2ef5-42f4-ac2e-c69d4a7cd2df) | BUG-013 |

---
