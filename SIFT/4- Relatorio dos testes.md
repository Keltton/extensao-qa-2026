# ✅ **Relatório Final de Execução de Testes – SIFIT**

**Sistema testado:** SIFIT – Sistema para Academias
**Responsável:** Keltton
**Data de execução:** 23/10/2026 - 
**Ambiente:**

* Sistema: SIFIT – Sistema para Academias
* URL: https://sifit.centrion.com.br
* Usuário: conta de teste fornecida pelo professor 
* Navegador: Google Chrome 
* Sistema operacional: Windows 11 

---

## 📊 **Resumo da Execução**

| Total de Casos de Teste | Casos Passaram | Casos Falharam | Bugs (casos) | Total de Bugs |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 17 | 7 | 10 | 10 | 10 |

---

## 🔍 **Cobertura por Módulo**

| Código RF | Módulo | Casos Testados | Passaram | Falharam | Bug(s) Associado(s) |
| --------- | ------ | :------------: | :------: | :------: | ------------------- |
| RF01 | Login e logout na plataforma | 5 | 3 | 2 | BUG-001, BUG-002 |
| RF02 | Página Inicial e indicadores | 3 | 1 | 2 | BUG-003, BUG-004 |
| RF03 | Gestão de clientes | 8 | 3 | 5 | BUG-005, BUG-006, BUG-007, BUG-008, BUG-009 |
| RF04 | Biblioteca de exercícios | 4 | 3 | 1 | BUG-010 |

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
| RF03 | C03-CT01 | Cadastrar cliente sem preencher campos obrigatórios | ✅ Passou | 
| RF03 | C03-CT02 | Cadastrar cliente com data de nascimento futura | ❌ Falhou | BUG-005 |
| RF03 | C03-CT03 | Editar cliente com dados válidos | ✅ Passou | - |
| RF03 | C03-CT04 | Editar cliente com CPF inválido | ❌ Falhou | BUG-006 |
| RF03 | C03-CT05 | Pesquisar cliente por nome | ✅ Passou | - |
| RF03 | C03-CT06 | Paginação mantendo o filtro de busca | ❌ Falhou | BUG-007 |
| RF03 | C03-CT07 | Filtro de status "Ativo" | ❌ Falhou | BUG-008 |
| RF03 | C03-CT08 | Visualizar a ficha de um cliente recém-cadastrado | ❌ Falhou | BUG-009 |
| RF04 | C04-CT01 | Cadastrar exercício sem nome | ✅ Passou | - |
| RF04 | C04-CT02 | Cadastrar exercício com dados válidos | ✅ Passou | - |
| RF04 | C04-CT03 | Cadastrar exercício duplicado no mesmo grupo | ❌ Falhou | BUG-010 |
| RF04 | C04-CT04 | Excluir exercício | ✅ Passou | - |

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
---

## 📈 **Resultado**

**Casos por status:**

* ✅ Passaram: 7
* ❌ Falharam: 10

**Severidade dos bugs:**

* 🟥 Alta: 1
* 🟨 Média: 5
* 🟩 Baixa: 4

---

## 🗄️ **Validação no Banco de Dados (MySQL Workbench)**

Consultas somente leitura para confirmar que o que aparece na tela foi gravado no banco:

```sql
-- Cliente de teste (C03-CT02 / C03-CT03): conferir nome e data de nascimento
SELECT id, nome, data_nascimento, sexo FROM pessoas WHERE nome LIKE 'Keltton%';
```
---

## 📁 **Evidências e Documentos**

* ✔️ Plano de Testes (Markdown)
* ✔️ Casos de Teste (Markdown – pasta `Cenarios de testes`)
* 🐛 Relatório de Bugs com evidências em vídeo e Registro de Melhorias
* 📹 Evidências em vídeo no Jam.dev; prints na pasta `Evidencias`

---

