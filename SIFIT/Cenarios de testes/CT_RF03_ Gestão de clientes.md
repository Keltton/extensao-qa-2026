## Cenário 03: Gestão de clientes.

### Caso de Teste 01: Cadastrar cliente sem preencher campos obrigatórios.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT01 | O sistema deve sinalizar todos os campos obrigatórios não preenchidos. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Clientes > "Novo Cliente" |
| **E** deixa Nome, Status, Sexo e Data de Nascimento em branco |
| **QUANDO** clicar em "Cadastrar Cliente" |
| **ENTÃO** todos os campos obrigatórios devem exibir mensagem de validação |

| **Critérios de aceitação** |
| :------------------------- |
| Cadastro bloqueado enquanto houver campo obrigatório vazio, com mensagem de validação. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Cadastro bloqueado; a validação é exibida um campo obrigatório por vez. | [Vídeo Jam](https://jam.dev/c/f2aad22c-c58f-477c-b89c-ddee7d230606) | - |

---

### Caso de Teste 02: Cadastrar cliente com data de nascimento futura.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT02 | Valor limite: a data de nascimento não pode ser posterior à data atual. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa "Novo Cliente" |
| **E** preenche Nome (nome de teste), Status "Ativo" e Sexo "Masculino" |
| **E** preenche Data de Nascimento "31/12/2027" |
| **QUANDO** clicar em "Cadastrar Cliente" |
| **ENTÃO** o sistema deve rejeitar a data futura |

| **Critérios de aceitação** |
| :------------------------- |
| Cadastro bloqueado com mensagem de data inválida. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Cliente cadastrado; a ficha exibe a idade "-2 anos". | [Vídeo Jam](https://jam.dev/c/f3cd80a9-c549-4e43-8957-182eaa983f3d) | BUG-005 |

---

### Caso de Teste 03: Editar cliente com dados válidos.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT03 | O sistema deve salvar alterações válidas no cadastro. |

| **Pré-condições** |
| :---------------- |
| Cliente de teste cadastrado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa a ficha do cliente de teste e clica em "Alterar dados" |
| **E** altera o Nome e a Data de Nascimento para uma data válida (ex.: "15/05/2000") |
| **QUANDO** clicar em "Salvar Alterações" |
| **ENTÃO** os dados devem ser gravados |

| **Critérios de aceitação** |
| :------------------------- |
| Ao reabrir a edição, os novos valores devem estar gravados. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Nome e data atualizados e persistidos. | [Vídeo Jam](https://jam.dev/c/205c0d3e-f429-45d3-ae76-949a2fc179be) | - |

---

### Caso de Teste 04: Salvar cliente com CPF inválido.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT04 | O sistema deve validar o dígito verificador do CPF. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está no cadastro ou na edição de um cliente |
| **E** preenche o CPF "111.111.111-11" |
| **QUANDO** clicar em "Cadastrar Cliente" / "Salvar Alterações" |
| **ENTÃO** o sistema deve exibir "CPF inválido" e não salvar |

| **Critérios de aceitação** |
| :------------------------- |
| CPF inválido rejeitado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | CPF 111.111.111-11 salvo sem nenhum aviso. | [Vídeo Jam](https://jam.dev/c/aee4435d-fdbd-4a84-bfe5-d8a28801ecd7) | BUG-006 |

---

### Caso de Teste 05: Pesquisar cliente por nome.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT05 | A busca deve retornar o cliente correspondente. |

| **Pré-condições** |
| :---------------- |
| Cliente de teste cadastrado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está em Clientes |
| **E** digita o nome do cliente de teste no filtro Nome |
| **QUANDO** clicar em "Buscar" |
| **ENTÃO** apenas os clientes com esse nome devem ser listados |

| **Critérios de aceitação** |
| :------------------------- |
| Resultado contém somente clientes correspondentes. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Retornou somente os clientes correspondentes ao nome pesquisado. | [Print](../Evidencias/C03-CT05.png) | - |

---

### Caso de Teste 06: Paginação mantendo o filtro de busca.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT06 | Ao trocar de página, o filtro aplicado deve ser mantido. |

| **Pré-condições** |
| :---------------- |
| Busca por nome realizada (C03-CT05). |

| **Passos** |
| :--------- |
| **DADO** que a busca por nome retornou resultados que cabem em uma única página |
| **QUANDO** o usuário clicar na página "2" da paginação |
| **ENTÃO** a paginação não deveria oferecer outras páginas, ou a página 2 deveria manter o filtro |

| **Critérios de aceitação** |
| :------------------------- |
| A paginação deve respeitar o resultado filtrado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | A paginação mostra 3 páginas para 1 resultado; a página 2 lista clientes que não correspondem à busca. | [Vídeo Jam](https://jam.dev/c/2359f24c-548d-4136-b968-1234c3f2770e) | BUG-007 |

---

### Caso de Teste 07: Filtro de status "Ativo".

| ID       | Descrição |
| :------- | :-------- |
| C03-CT07 | Com o filtro Status = Ativo, apenas clientes ativos devem ser listados. |

| **Pré-condições** |
| :---------------- |
| Existirem clientes ativos e inativos. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Clientes |
| **E** o filtro Status está como "Ativo" |
| **QUANDO** a lista for exibida |
| **ENTÃO** nenhum cliente INATIVO deve aparecer |

| **Critérios de aceitação** |
| :------------------------- |
| Apenas clientes ativos listados. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | A lista exibe clientes com status INATIVO com o filtro em "Ativo". | [Vídeo Jam](https://jam.dev/c/a6adccf3-ae4c-47f8-9343-8ad793e5758e) | BUG-008 |

---

### Caso de Teste 08: Visualizar a ficha de um cliente recém-cadastrado.

| ID       | Descrição |
| :------- | :-------- |
| C03-CT08 | A ficha deve exibir apenas dados reais do cliente. |

| **Pré-condições** |
| :---------------- |
| Cliente de teste cadastrado sem telefone e sem endereço. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Clientes > Visualizar no cliente de teste |
| **QUANDO** a ficha for carregada |
| **ENTÃO** os campos vazios devem aparecer em branco ou com "-", sem dados fictícios |

| **Critérios de aceitação** |
| :------------------------- |
| Nenhum "null" ou dado fictício na ficha. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | O telefone aparece como "null"; o Bairro aparece como "null" na edição; o card "Objetivos" exibe "Perda de peso e ganho de resistência" e "Progresso geral 60%" para um cliente sem nenhum dado. | [Vídeo Jam](https://jam.dev/c/a4c73bde-5ac1-43ad-8a47-3ebde1f4e346) | BUG-009 |

---
