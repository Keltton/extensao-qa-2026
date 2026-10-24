## 🧪 **Plano de Testes – SIFIT**

### 📌 1. **Identificação**

* **Nome do Projeto**: SIFIT – Sistema para Academias
* **Versão Avaliada**: ambiente de aula (sifit.centrion.com.br)
* **Ambiente de Testes**: [https://sifit.centrion.com.br](https://sifit.centrion.com.br)
* **Banco de dados**: MySQL (acesso de leitura via MySQL Workbench)
* **Tipo de Teste**: Teste Funcional Manual
* **Data do Documento**: 23/10/2026
* **Responsável**: Keltton

---

### 🎯 2. **Objetivo**

Verificar manualmente os requisitos funcionais centrais do SIFIT (autenticação, página inicial, clientes, exercícios, planos, matrículas, contas a receber e check-in), validando fluxos principais, mensagens de erro, regras de negócio e a integração entre módulos (matrícula → contas a receber → indicadores).

---

### 🧩 3. **Escopo**

**Incluído:** RF01 a RF08 (ver Análise de Requisitos).

**Excluído:**

* Demais módulos do menu (listados na Análise de Requisitos)
* Integração real com o gateway Pagar.me (nenhuma cobrança foi gerada)
* Testes em dispositivos móveis, de performance, carga e segurança

---

### 🔧 4. **Ferramentas Utilizadas**

* Navegador Google Chrome
* DevTools do Chrome – F12 (console e inspeção de elementos)
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
| Criação dos Casos de Teste  | 23/10/2026  | 23/10/2026 |
| Execução dos Testes Manuais | 23/10/2026  | 24/10/2026 |
| Registro de Bugs            | 23/10/2026  | 24/10/2026 |
| Gravação das evidências     | 23/10/2026  | 24/10/2026 |


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
| Ambiente compartilhado com a turma (dados alterados por terceiros) | Alto | Usar dados de teste identificáveis e não depender de IDs fixos na documentação |
| Gerar cobrança real pelo Pagar.me | Alto | Não usar "Salvar também na Pagar.me"; manter "Pag. Via Sistema" = Não |
| Dados pessoais reais na base | Alto | Não publicar prints com nome ou CPF de terceiros (LGPD) |
| Banco de dados somente leitura | Médio | Validações no banco feitas apenas com SELECT |
| Sistema fora do ar | Médio | Repetir a execução depois |

---

### 🧾 12. **Dados de Teste Criados**

| Tipo | Identificação |
| ---- | ------------- |
| Cliente | Cliente de teste (cadastrado em C03-CT02 e editado em C03-CT03) |
| Exercício | Exercício de teste no grupo Peitoral (C04-CT02) |
| Plano | Plano de teste (C05-CT04) |
| Matrícula | Matrícula do cliente de teste no plano de teste (C06-CT02) |
| Conta a receber | Parcela gerada pela matrícula (C07-CT01) |
| Check-in | Check-in do cliente de teste (C08-CT03) |

> Os códigos e nomes dos registros não são fixados neste documento porque o ambiente é compartilhado e os dados são alterados por outras pessoas.

---
