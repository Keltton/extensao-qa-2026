## Cenário 01: Login e logout na plataforma.

### Caso de Teste 01: Login com credenciais válidas.

| ID       | Descrição |
| :------- | :-------- |
| C01-CT01 | O login será realizado com usuário e senha válidos. |

| **Pré-condições** |
| :---------------- |
| Credenciais de teste fornecidas pelo professor. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página de login do SIFIT |
| **E** preenchemos o usuário válido no campo "Login" |
| **E** preenchemos a senha válida no campo "Senha" |
| **QUANDO** clicarmos em "Entrar" |
| **ENTÃO** seremos redirecionados para a Página Inicial (/dashboard) |

| **Critérios de aceitação** |
| :------------------------- |
| O redirecionamento para a Página Inicial deve ocorrer, com saudação ao usuário logado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Redirecionado para /dashboard com a mensagem "Boa noite, <usuário>!". | [Vídeo Jam](https://jam.dev/c/90dcfc9e-0266-42bc-b771-c8641c787242) | - |

---

### Caso de Teste 02: Login com usuário inexistente e senha inválida.

| ID       | Descrição |
| :------- | :-------- |
| C01-CT02 | O login deve falhar e exibir mensagem de erro. |

| **Pré-condições** |
| :---------------- |
| Nenhuma. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página de login do SIFIT |
| **E** preenchemos "usuario_inexistente_qa" no campo "Login" |
| **E** preenchemos "senhaerrada" no campo "Senha" |
| **QUANDO** clicarmos em "Entrar" |
| **ENTÃO** deve ser exibida uma mensagem de credenciais inválidas |

| **Critérios de aceitação** |
| :------------------------- |
| Mensagem de erro exibida e usuário permanece na tela de login. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Exibida a mensagem "O nome de usuário e senha não correspondem.". | [Vídeo Jam](https://jam.dev/c/461b0484-4a78-4535-81d5-c3542770ff27) | - |

---

### Caso de Teste 03: Login com campos em branco.

| ID       | Descrição |
| :------- | :-------- |
| C01-CT03 | O sistema deve validar os campos obrigatórios antes de enviar o formulário. |

| **Pré-condições** |
| :---------------- |
| Nenhuma. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página de login do SIFIT |
| **E** deixamos os campos "Login" e "Senha" em branco |
| **QUANDO** clicarmos em "Entrar" |
| **ENTÃO** deve ser exibida mensagem de campo obrigatório em cada campo |

| **Critérios de aceitação** |
| :------------------------- |
| Os campos obrigatórios devem exibir mensagens de validação. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | O formulário é enviado e retorna "O nome de usuário e senha não correspondem."; não há validação de campo obrigatório. | [Vídeo Jam](https://jam.dev/c/b5ac054d-c990-408c-9c9f-6c8087c157f4) | BUG-001 |

---

### Caso de Teste 04: Recuperação de senha.

| ID       | Descrição |
| :------- | :-------- |
| C01-CT04 | O link "Esqueci minha senha" deve iniciar o fluxo de recuperação. |

| **Pré-condições** |
| :---------------- |
| Nenhuma. |

| **Passos** |
| :--------- |
| **DADO** que estamos na página de login do SIFIT |
| **QUANDO** clicarmos em "Esqueci minha senha" |
| **ENTÃO** deve ser exibida uma tela ou modal para recuperar a senha |

| **Critérios de aceitação** |
| :------------------------- |
| O fluxo de recuperação de senha deve ser iniciado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Nada acontece; o link aponta para "#". | [Vídeo Jam](https://jam.dev/c/672ead1f-39f8-4e51-bca7-92fc6ebf8e1a) | BUG-002 |

---

### Caso de Teste 05: Logout e acesso a rota protegida.

| ID       | Descrição |
| :------- | :-------- |
| C01-CT05 | Após sair, o sistema não deve permitir acesso às telas internas. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está logado |
| **E** abre o menu do usuário e clica em "Sair do sistema" |
| **QUANDO** acessar diretamente a URL /clientes |
| **ENTÃO** deve ser redirecionado para a tela de login |

| **Critérios de aceitação** |
| :------------------------- |
| Sessão encerrada e rotas internas protegidas. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Redirecionado para /login nas duas situações. | [Vídeo Jam](https://jam.dev/c/06bd8930-85a1-4de6-8889-eb73d57b799d) | - |

---
