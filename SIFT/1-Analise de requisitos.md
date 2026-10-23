## 📦 **Requisitos Funcionais – SIFIT (para testes manuais)**

Levantamento feito por navegação no sistema em 19/10/2026-22/10/2026. Foi selecionado do sistema SIFT os 8 módulos Centrais da sua operação (fluxo cliente → plano → matrícula → financeiro → presença).

---

### 🔐 **RF01 - Autenticação**

**Descrição**: O sistema deve controlar o acesso por usuário e senha.

* **Funcionalidades esperadas**:

  * Login com usuário e senha válidos
  * Mensagem de erro para credenciais inválidas
  * Validação de campos obrigatórios
  * Recuperação de senha ("Esqueci minha senha")
  * Opção "Manter conectado"
  * Logout e proteção das rotas internas

---

### 🏠 **RF02 - Página Inicial**

**Descrição**: Após o login, exibir o resumo da academia.

* **Funcionalidades esperadas**:

  * Saudação ao usuário e data atual
  * Cards: alunos em risco, valor em aberto, pico de movimento, avaliações pendentes
  * Cards: clientes ativos, ausentes, sem matrícula, personais, matrículas, desistências, renovações
  * Filtro de período (data inicial e final)

---

### 👤 **RF03 - Gestão de Clientes**

**Descrição**: Cadastrar, consultar, editar e excluir clientes (alunos).

* **Funcionalidades esperadas**:

  * Listagem com filtros por código, nome, status, situação, plano e personal
  * Paginação (20/50/100 por página)
  * Cadastro com identificação, documentos, foto, contato, endereço, acesso e responsável
  * Campos obrigatórios: Nome, Status, Sexo, Data de Nascimento
  * Visualização da ficha (dados, desempenho, matrícula atual)
  * Edição ("Alterar dados") e exclusão

---

### 🏋️ **RF04 - Biblioteca de Exercícios**

**Descrição**: Manter os exercícios agrupados por grupo muscular.

* **Funcionalidades esperadas**:

  * Listagem por grupo muscular com total
  * Adicionar exercício (código, nome obrigatório, imagem e vídeo opcionais)
  * Visualizar e excluir exercício com confirmação

---

### 📋 **RF05 - Gestão de Planos**

**Descrição**: Manter os planos comercializados pela academia.

* **Funcionalidades esperadas**:

  * Listagem com filtros por código, nome e status
  * Cards: total, ativos, alunos em planos, receita estimada, ranking
  * Cadastro: nome, grupo, status, cobrança, parcelas, valor mensal, valor de matrícula, personal, dependentes, benefícios
  * Opção de salvar também no gateway Pagar.me

---

### 📝 **RF06 - Matrículas**

**Descrição**: Vincular cliente a um plano e gerar as parcelas.

* **Funcionalidades esperadas**:

  * Listagem com filtros e cards (ativas, recorrentes, não renovadas, do mês)
  * Seleção do cliente por pesquisa (lupa)
  * Seleção da modalidade (plano), tipo de pagamento, dia de vencimento, desconto
  * Definição da quantidade de parcelas
  * Opção de pagar a primeira parcela e aplicar anamnese após salvar

---

### 💰 **RF07 - Contas a Receber**

**Descrição**: Controlar os recebimentos da academia.

* **Funcionalidades esperadas**:

  * Filtros por código, nome, tipo de data (vencimento/recebimento), período e status
  * Atalhos de período (hoje, ontem, 7 dias, este mês)
  * Cards: entradas, saídas, líquido, previsto, recebido, pendentes, atrasadas
  * Geração automática das parcelas a partir da matrícula

---

### ✅ **RF08 - Check-in**

**Descrição**: Registrar e acompanhar a presença dos alunos.

* **Funcionalidades esperadas**:

  * Entrada rápida pelo código do cliente (ou QR Code)
  * Lista do dia com plano, horário de entrada/saída e status
  * Cards: check-ins hoje, presentes agora, meta do dia, média diária, taxa de frequência
  * Gráfico de pico de movimento