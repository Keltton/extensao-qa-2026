## Cenário 05: Gestão de planos.

### Caso de Teste 01: Salvar plano em branco.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT01 | O nome do plano é obrigatório. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Planos > "Novo Plano" |
| **QUANDO** clicar em "Salvar Plano" sem preencher nada |
| **ENTÃO** o campo Nome deve ser sinalizado como obrigatório |

| **Critérios de aceitação** |
| :------------------------- |
| Cadastro bloqueado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Validação do navegador exibida no campo Nome. | [Print](../Evidencias/C05-CT01.png) | - |

---

### Caso de Teste 02: Valor mensal negativo.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT02 | Valor limite: o valor do plano não pode ser negativo. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está no formulário "Novo Plano" |
| **QUANDO** digitar "-50" no campo Valor Mensal |
| **ENTÃO** o sistema não deve aceitar valor negativo |

| **Critérios de aceitação** |
| :------------------------- |
| Sinal negativo ignorado ou rejeitado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | A máscara ignorou o sinal "-" (campo ficou 0,50). | [Print](../Evidencias/C05-CT02.png) | - |

---

### Caso de Teste 03: Cadastrar plano sem selecionar o Grupo.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT03 | Campos obrigatórios devem ser sinalizados; erros devem ser claros. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário preenche Nome (nome de teste), Valor Mensal 99,90, Parcelas 1 e Valor Matrícula 10,00 |
| **E** não seleciona o Grupo (campo sem opção selecionada e sem indicação de obrigatório) |
| **QUANDO** clicar em "Salvar Plano" |
| **ENTÃO** o sistema deve indicar que o Grupo é obrigatório |

| **Critérios de aceitação** |
| :------------------------- |
| Mensagem clara apontando o campo faltante. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Modal genérico "Erro ao salvar plano"; o console mostra HTTP 500. O Grupo não é sinalizado. | [Vídeo Jam](https://jam.dev/c/e906f237-50f5-4b44-a6fc-bcf29f187904) | BUG-011 |

---

### Caso de Teste 04: Cadastrar plano com dados válidos.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT04 | O plano deve ser cadastrado e listado. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário preenche o plano como em C05-CT03 |
| **E** seleciona o Grupo "Treino Livre" |
| **QUANDO** clicar em "Salvar Plano" |
| **ENTÃO** o plano deve aparecer na listagem |

| **Critérios de aceitação** |
| :------------------------- |
| Plano listado e contador atualizado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Plano listado (R$ 99,90, Mensalidade, ATIVO). | [Vídeo Jam](https://jam.dev/c/07d5dec8-95a9-43f2-b9fe-59af7f25b87a) | - |

---

### Caso de Teste 05: Filtrar planos por status Inativo.

| ID       | Descrição |
| :------- | :-------- |
| C05-CT05 | O filtro deve listar apenas planos inativos. |

| **Pré-condições** |
| :---------------- |
| Existirem planos ativos e inativos. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está em Planos |
| **E** seleciona Status "Inativo" |
| **QUANDO** clicar em "Buscar" |
| **ENTÃO** apenas planos INATIVOS devem ser listados |

| **Critérios de aceitação** |
| :------------------------- |
| Somente planos inativos. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Somente planos INATIVOS listados; quantidade coerente com o total de planos menos os ativos. | [Print](../Evidencias/C05-CT05.png) | - |

---
