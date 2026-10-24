## 🧪 **Plano de Testes – SIFIT**

### 📌 1. **Identificação**

* **Nome do Projeto**: SIFIT – Sistema para Academias
* **Versão Avaliada**: ambiente de aula (sifit.centrion.com.br)
* **Ambiente de Testes**: [https://sifit.centrion.com.br](https://sifit.centrion.com.br)
* **Banco de dados**: MySQL (acesso de leitura via MySQL Workbench)
* **Tipo de Teste**: Teste Funcional Manual
* **Data do Documento**: 19/10/2026
* **Responsável**: Keltton

---

### 🎯 2. **Objetivo**

Verificar manualmente os requisitos funcionais centrais do SIFIT (autenticação, página inicial, clientes, exercícios, planos, matrículas, contas a receber e check-in), validando fluxos principais, mensagens de erro, regras de negócio e a integração entre módulos (matrícula → contas a receber → indicadores).

---

### 🧩 3. **Escopo**

**Incluído:** RF01 a RF08 (ver Análise de Requisitos).

---

### 🔧 4. **Ferramentas Utilizadas**

* Navegador Google Chrome / Chromium
* Tools4dev (console e inspeção de elementos)
* Jam.dev (gravação das evidências em vídeo)
* MySQL Workbench (consulta ao banco)
* GitHub (documentação em Markdown)

---

### 🧪 5. **Técnicas de Teste**

* Caminho feliz (Happy Path)
* Testes negativos (campos vazios, dados inválidos)
* Particionamento de equivalência (CPF válido/inválido, código existente/inexistente)
* Análise de valor limite (data de nascimento futura, valor negativo, período invertido)
* Teste exploratório (indicadores e consistência entre telas)

---

### 📄 6. **Critérios de Aceitação**

* Todos os casos devem produzir o resultado esperado.
* Nenhuma falha de severidade Alta nos fluxos principais.
* Mensagens de erro claras e em português.
* Dados exibidos coerentes entre módulos.

---

### 🚦 7. **Critérios de Saída (Exit Criteria)**

* 100% dos casos planejados executados.
* Falhas registradas no Relatório de Bugs com evidência e caso relacionado.
* Relatório final com números iguais aos dos cenários.

---

### ⏱️ 8. **Cronograma**

| Atividade                   | Data Início | Data Fim   |
| --------------------------- | ----------- | ---------- |
| Levantamento de requisitos  | 17/10/2026  | 22/10/2026 |
| Planejamento de Testes      | 22/10/2026  | 23/10/2026 |
| Criação dos Casos de Teste  | 23/10/2026  |     -      |
| Execução dos Testes Manuais | 23/10/2026  |     -      |
| Registro de Bugs            | 23/10/2026  |     -      |
| Gravação das evidências     | 23/10/2026  |     -      |


---

### 📋 9. **Módulos a Serem Testados**

| Código RF | Módulo | Prioridade |
| --------- | ------ | ---------- |
| RF01 | Autenticação | Alta |
| RF02 | Página Inicial | Média |
| RF03 | Gestão de Clientes | Alta |
| RF04 | Biblioteca de Exercícios | Média |
| RF05 | Gestão de Planos | Alta |
| RF06 | Matrículas | Alta |
| RF07 | Contas a Receber | Alta |
| RF08 | Check-in | Média |

---

### 🐞 10. **Gestão de Defeitos**

* Cada bug é documentado com: ID, título, descrição, severidade, prioridade, status, passos, esperado × obtido, ambiente, funcionalidade, caso relacionado e evidência.
* **Severidade**: Crítica, Alta, Média ou Baixa (impacto no sistema).
* **Prioridade**: Alta, Média ou Baixa (urgência de correção para o negócio).

---

### 📌 11. **Riscos Identificados**

| Risco | Impacto | Mitigação |
| ----- | ------- | --------- |

---

### 🧾 12. **Dados de Teste Criados**

| Tipo | Identificação |
| ---- | ------------- |
| Cliente | #414 "Keltton Felipe" |
| Exercício | "teste" (grupo Peitoral) |

---