# Relatório de Bugs

**Software:** SIFIT – Sistema para Academias

**QA responsável:** Keltton

**Data:** 23/10/2026 -

---

### 🐞 **BUG-001: Login com campos vazios não valida campos obrigatórios**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-001 | Ao clicar em "Entrar" com Login e Senha vazios, o formulário é enviado ao servidor e retorna mensagem de credenciais incorretas, em vez de indicar os campos obrigatórios. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Acessar a página de login |
| 2. Deixar Login e Senha em branco |
| 3. Clicar em "Entrar" |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Mensagem de campo obrigatório em cada campo, sem enviar o formulário | Mensagem "O nome de usuário e senha não correspondem." |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor  |
| Navegador: Google Chrome  |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Login | C01-CT03 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/b5ac054d-c990-408c-9c9f-6c8087c157f4) |

---

### 🐞 **BUG-002: Link "Esqueci minha senha" não executa nenhuma ação**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-002 | O link de recuperação de senha aponta para "#" e não abre tela nem modal, impedindo o usuário de recuperar o acesso. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Alta | Alta | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Acessar a página de login |
| 2. Clicar em "Esqueci minha senha" |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Abrir o fluxo de recuperação de senha | Nada acontece |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Login / Recuperação de senha | C01-CT04 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/672ead1f-39f8-4e51-bca7-92fc6ebf8e1a) |

---

### 🐞 **BUG-003: Card "em aberto" da Página Inicial ignora contas pendentes**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-003 | O card da Página Inicial mostra R$ 0,00 em aberto. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Cadastrar uma matrícula que gere parcela pendente no mês |
| 2. Acessar a Página Inicial |
| 3. Observar o card "em aberto" |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Demonstrar o pagamento pendente em aberto | R$ 0,00 em aberto |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor (credenciais não publicadas) |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Página Inicial | C02-CT02 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/a6cc5c0a-010c-4f85-8aa3-762e5c4ec3a0) |

---

### 🐞 **BUG-004: Filtro de período aceita data inicial maior que a final**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-004 | É possível selecionar o período 31/10/2026 a 01/10/2026; o sistema não alerta e continua exibindo indicadores. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Acessar a Página Inicial |
| 2. Selecionar 31/10/2026 como data inicial |
| 3. Selecionar 01/10/2026 como data final |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Bloquear datas anteriores à inicial ou exibir aviso | Período invertido aceito; cards exibem valores (ex.: 2 matrículas no período) |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Página Inicial | C02-CT03 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/5f7f9e52-3989-42d5-99c2-66b747dec9e3) |

---

### 🐞 **BUG-005: Cadastro aceita data de nascimento futura e exibe idade negativa**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-005 | O cliente foi salvo com nascimento em 31/12/2027 e a ficha mostra "-2 anos". |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Média | Alta | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Clientes > Novo Cliente |
| 2. Preencher Nome, Status e Sexo |
| 3. Data de Nascimento 31/12/2027  |
| 4. Cadastrar Cliente |
| 5. Abrir a ficha do cliente |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Rejeitar data futura | Cliente #414 salvo; idade "-2 anos" |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Cadastro de cliente | C03-CT02 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/f3cd80a9-c549-4e43-8957-182eaa983f3d) |

---

### 🐞 **BUG-006: CPF inválido é aceito no cadastro de cliente**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-006 | O CPF 111.111.111-11 (dígitos repetidos, inválido) foi salvo sem validação. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Média | Alta | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Abrir a edição de um cliente |
| 2. Preencher CPF 111.111.111-11 |
| 3. Salvar Alterações |
| 4. Reabrir a edição |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Mensagem "CPF inválido" e bloqueio do salvamento | CPF salvo |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Cadastro de cliente | C03-CT04 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/aee4435d-fdbd-4a84-bfe5-d8a28801ecd7) |

---

### 🐞 **BUG-007: Paginação de clientes descarta o filtro de busca**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-007 | Com 2 resultado na busca por "Keltton", a paginação mostra 3 páginas e a página lista clientes que não correspondem ao filtro. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Média | Média | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Clientes |
| 2. Filtrar Nome = "Keltton" e Buscar |
| 3. Clicar na página 2 |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Apenas 1 página, ou página 2 respeitando o filtro | 3 páginas; página 2 com clientes não relacionados (ex.: #261 "Keltton") |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Listagem de clientes | C03-CT06 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/2359f24c-548d-4136-b968-1234c3f2770e) |

---

### 🐞 **BUG-008: Filtro de status "Ativo" lista clientes inativos**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-008 | Com o filtro padrão Status = Ativo, a lista exibe clientes INATIVOS. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Média | Alta | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Acessar Clientes |
| 2. Manter Status = Ativo |
| 3. Observar a coluna Status |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Somente clientes ATIVOS | Clientes INATIVOS listados (ex.: #397, #393, #392) |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Listagem de clientes | C03-CT07 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/a6adccf3-ae4c-47f8-9343-8ad793e5758e) |

---

### 🐞 **BUG-009: Ficha do cliente exibe "null" e objetivos fictícios**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-009 | Em cliente sem telefone e sem endereço, aparece o texto "null" e um card de objetivos com texto e progresso de 60% que não foram cadastrados. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Baixa | Média | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Cadastrar cliente sem telefone e sem endereço |
| 2. Abrir Visualizar Cliente |
| 3. Abrir Alterar dados e observar o Bairro |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Campos vazios em branco ou "-"; objetivos vazios | "null" no telefone e no Bairro; objetivos "Perda de peso..." com 60% |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome / Chromium |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Ficha do cliente | C03-CT08 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/a4c73bde-5ac1-43ad-8a47-3ebde1f4e346) |

---

### 🐞 **BUG-010: Exercício duplicado é aceito no mesmo grupo muscular**

| **ID** | **Descrição** |
| ------ | ------------- |
| BUG-010 | É possível cadastrar dois exercícios com o mesmo nome no mesmo grupo. |

| **Severidade do Bug** | **Prioridade de Correção** | **Status** |
| :-------------------: | :------------------------: | :--------: |
| Baixa | Baixa | Aberto |

| **Passo a passo para simular o bug** |
| ------------------------------------ |
| 1. Exercícios > Adicionar (Peitoral) |
| 2. Cadastrar "teste" |
| 3. Repetir o cadastro com o mesmo nome |

| **Comportamento Esperado** | **Comportamento Obtido** |
| :------------------------: | :----------------------: |
| Aviso de exercício já existente | Dois itens iguais no grupo |

| **Ambiente** |
| ------------ |
| URL: https://sifit.centrion.com.br |
| Usuário: conta de teste fornecida pelo professor |
| Navegador: Google Chrome |

| **Funcionalidade Afetada** | **Caso de Teste Relacionado** |
| :------------------------: | :---------------------------: |
| Exercícios | C04-CT03 |

| **Evidência(s)** |
| :--------------: |
| [Vídeo Jam](https://jam.dev/c/a84d54b0-8ca9-4871-9a16-5c563024a8f4) |

---
