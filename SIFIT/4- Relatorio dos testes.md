# ✅ **Relatório Final de Execução de Testes – SIFIT**

**Sistema testado:** SIFIT – Sistema para Academias
**Responsável:** Keltton
**Data de execução:** 23/10/2026 a 24/10/2026
**Ambiente:**

* Sistema: SIFIT – Sistema para Academias
* URL: https://sifit.centrion.com.br
* Usuário: conta de teste fornecida pelo professor
* Navegador: Google Chrome
* Sistema operacional: Windows 11

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs Registrados |
| :---: | :---: | :---: | :---: |
| 38 | 21 | 17 | 17 |

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo | Casos Testados | Passaram | Falharam | Bug(s) Associado(s) |
| --------- | ------ | :------------: | :------: | :------: | ------------------- |
| RF01 | Login e logout na plataforma | 5 | 3 | 2 | BUG-001, BUG-002 |
| RF02 | Página Inicial e indicadores | 3 | 1 | 2 | BUG-003, BUG-004 |
| RF03 | Gestão de clientes | 8 | 3 | 5 | BUG-005, BUG-006, BUG-007, BUG-008, BUG-009 |
| RF04 | Biblioteca de exercícios | 4 | 3 | 1 | BUG-010 |
| RF05 | Gestão de planos | 5 | 4 | 1 | BUG-011 |
| RF06 | Matrículas | 4 | 2 | 2 | BUG-012, BUG-013 |
| RF07 | Contas a Receber | 4 | 3 | 1 | BUG-014 |
| RF08 | Check-in | 5 | 2 | 3 | BUG-015, BUG-016, BUG-017 |

---

## 🧭 **Matriz de Rastreabilidade (Requisito → Caso → Resultado → Bug)**

| RF | Caso | Título | Resultado | Bug |
| -- | ---- | ------ | :-------: | --- |
| RF01 | C01-CT01 | Login com credenciais válidas | ✅ Passou | - |
| RF01 | C01-CT02 | Login com usuário inexistente e senha inválida | ✅ Passou | - |
| RF01 | C01-CT03 | Login com campos em branco | ❌ Falhou | BUG-001 |
| RF01 | C01-CT04 | Recuperação de senha | ❌ Falhou | BUG-002 |
| RF01 | C01-CT05 | Logout e acesso a rota protegida | ✅ Passou | - |
| RF02 | C02-CT01 | Exibição dos indicadores após o login | ✅ Passou | - |
| RF02 | C02-CT02 | Card "em aberto" reflete contas pendentes | ❌ Falhou | BUG-003 |
| RF02 | C02-CT03 | Filtro de período com data inicial maior que a final | ❌ Falhou | BUG-004 |
| RF03 | C03-CT01 | Cadastrar cliente sem preencher campos obrigatórios | ✅ Passou | - |
| RF03 | C03-CT02 | Cadastrar cliente com data de nascimento futura | ❌ Falhou | BUG-005 |
| RF03 | C03-CT03 | Editar cliente com dados válidos | ✅ Passou | - |
| RF03 | C03-CT04 | Salvar cliente com CPF inválido | ❌ Falhou | BUG-006 |
| RF03 | C03-CT05 | Pesquisar cliente por nome | ✅ Passou | - |
| RF03 | C03-CT06 | Paginação mantendo o filtro de busca | ❌ Falhou | BUG-007 |
| RF03 | C03-CT07 | Filtro de status "Ativo" | ❌ Falhou | BUG-008 |
| RF03 | C03-CT08 | Visualizar a ficha de um cliente recém-cadastrado | ❌ Falhou | BUG-009 |
| RF04 | C04-CT01 | Cadastrar exercício sem nome | ✅ Passou | - |
| RF04 | C04-CT02 | Cadastrar exercício com dados válidos | ✅ Passou | - |
| RF04 | C04-CT03 | Cadastrar exercício duplicado no mesmo grupo | ❌ Falhou | BUG-010 |
| RF04 | C04-CT04 | Excluir exercício | ✅ Passou | - |
| RF05 | C05-CT01 | Salvar plano em branco | ✅ Passou | - |
| RF05 | C05-CT02 | Valor mensal negativo | ✅ Passou | - |
| RF05 | C05-CT03 | Cadastrar plano sem selecionar o Grupo | ❌ Falhou | BUG-011 |
| RF05 | C05-CT04 | Cadastrar plano com dados válidos | ✅ Passou | - |
| RF05 | C05-CT05 | Filtrar planos por status Inativo | ✅ Passou | - |
| RF06 | C06-CT01 | Salvar matrícula sem cliente | ✅ Passou | - |
| RF06 | C06-CT02 | Cadastrar matrícula válida | ✅ Passou | - |
| RF06 | C06-CT03 | Data da parcela aceita data inválida | ❌ Falhou | BUG-012 |
| RF06 | C06-CT04 | Matrícula oferece apenas planos ativos | ❌ Falhou | BUG-013 |
| RF07 | C07-CT01 | Conta gerada pela matrícula (busca por nome) | ✅ Passou | - |
| RF07 | C07-CT02 | Listagem do período sem filtro de nome | ✅ Passou | - |
| RF07 | C07-CT03 | Filtro por status Pendente | ✅ Passou | - |
| RF07 | C07-CT04 | Cards de resumo consideram contas pendentes | ❌ Falhou | BUG-014 |
| RF08 | C08-CT01 | Check-in com código em branco | ❌ Falhou | BUG-015 |
| RF08 | C08-CT02 | Check-in com código inexistente | ✅ Passou | - |
| RF08 | C08-CT03 | Check-in de cliente com matrícula ativa | ✅ Passou | - |
| RF08 | C08-CT04 | Horário do check-in corresponde ao horário local | ❌ Falhou | BUG-016 |
| RF08 | C08-CT05 | Status e "Presentes agora" após o check-in | ❌ Falhou | BUG-017 |

---

## 🐞 **Resumo dos Bugs Reportados**

| ID | Título | Severidade | Prioridade | Status |
| -- | ------ | ---------- | ---------- | ------ |
| BUG-001 | Login com campos vazios não valida campos obrigatórios | Baixa | Baixa | Aberto |
| BUG-002 | Link "Esqueci minha senha" não executa nenhuma ação | Alta | Alta | Aberto |
| BUG-003 | Card "em aberto" da Página Inicial ignora contas pendentes | Média | Média | Aberto |
| BUG-004 | Filtro de período aceita data inicial maior que a final | Baixa | Baixa | Aberto |
| BUG-005 | Cadastro aceita data de nascimento futura e exibe idade negativa | Média | Alta | Aberto |
| BUG-006 | CPF inválido é aceito no cadastro de cliente | Média | Alta | Aberto |
| BUG-007 | Paginação de clientes descarta o filtro de busca | Média | Média | Aberto |
| BUG-008 | Filtro de status "Ativo" lista clientes inativos | Média | Alta | Aberto |
| BUG-009 | Ficha do cliente exibe "null" e objetivos fictícios | Baixa | Média | Aberto |
| BUG-010 | Exercício duplicado é aceito no mesmo grupo muscular | Baixa | Baixa | Aberto |
| BUG-011 | Cadastro de plano sem Grupo retorna erro 500 genérico | Média | Alta | Aberto |
| BUG-012 | Campo Data do modal de parcelas aceita data inválida | Média | Média | Aberto |
| BUG-013 | Nova matrícula permite selecionar plano inativo | Alta | Alta | Aberto |
| BUG-014 | Cards de Contas a Receber não refletem as contas pendentes | Média | Alta | Aberto |
| BUG-015 | Check-in com código vazio não exibe aviso | Baixa | Baixa | Aberto |
| BUG-016 | Horário do check-in registrado 3 horas à frente do horário local | Média | Alta | Aberto |
| BUG-017 | Cliente com entrada registrada continua "Pendente" e fora de "Presentes agora" | Média | Média | Aberto |

---

## 📈 **Resultado**

**Casos por status:**

* ✅ Passaram: 21
* ❌ Falharam: 17

**Severidade dos bugs:**

* 🟥 Alta: 2
* 🟨 Média: 10
* 🟩 Baixa: 5

---

## 🗄️ **Validação no Banco de Dados (MySQL Workbench)**

Consulta somente leitura para confirmar que o que aparece na tela foi gravado no banco:

```sql
-- Cliente de teste (C03-CT02 / C03-CT03): conferir nome e data de nascimento
-- Substitua pelo nome usado no cadastro de teste
SELECT id, nome, data_nascimento, sexo FROM pessoas WHERE nome LIKE '%nome_do_teste%';
```

> A coluna `cpf` da tabela `pessoas` é armazenada criptografada; por isso a validação do CPF inválido (BUG-006) é feita pela tela de edição.

---

## 📁 **Evidências e Documentos**

* ✔️ Análise de Requisitos e Plano de Testes (Markdown)
* ✔️ Casos de Teste (Markdown – pasta `Cenarios de testes`)
* 🐛 Relatório de Bugs com evidências em vídeo
* 📹 Evidências em vídeo no Jam.dev; prints na pasta `Evidencias`

---

## ✅ **Conclusão**

Os fluxos principais do SIFIT (login, cadastro de cliente, exercício, plano, matrícula, geração da conta a receber e check-in) **funcionam no caminho feliz**, mas a execução encontrou **17 bugs**, sendo 2 de severidade alta: a **recuperação de senha não funciona** e a **matrícula permite plano inativo**. Os demais se concentram em **validação de dados** (data de nascimento futura, CPF inválido, data inválida nas parcelas, duplicidade, campo obrigatório não sinalizado), **filtros e paginação** de clientes e **indicadores** que não refletem os dados reais (valor em aberto, cards de Contas a Receber, status do check-in e fuso horário).

### 🔍 Identificação da Causa Raiz (Root Cause Analysis)

| Grupo de bugs | Causa raiz provável |
| ------------- | ------------------- |
| BUG-001, 005, 006, 010, 011, 012, 015 | Validações ausentes ou parciais no front-end e sem regra no back-end (dados inválidos chegam ao banco; campo faltante gera HTTP 500) |
| BUG-007, 008 | Filtros não enviados na listagem inicial e na troca de página |
| BUG-003, 014, 017 | Indicadores calculados com consulta diferente da usada nas listagens |
| BUG-016 | Data/hora gravada em UTC sem conversão para America/Sao_Paulo |
| BUG-009 | Componentes da ficha com valores fixos (mock) e campos nulos exibidos como "null" |
| BUG-002, 004, 013 | Regras de negócio não implementadas (recuperação de senha, validação de período, filtro de plano ativo) |

Técnica utilizada: **5 Porquês**, a partir do comportamento observado na tela, no console do navegador (HTTP 500) e na comparação entre telas.
