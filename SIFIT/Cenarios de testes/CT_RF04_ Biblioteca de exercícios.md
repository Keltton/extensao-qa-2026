## Cenário 04: Biblioteca de exercícios.

### Caso de Teste 01: Cadastrar exercício sem nome.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT01 | O nome do exercício é obrigatório. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Exercícios e clica em "Adicionar" no grupo Peitoral |
| **E** deixa o Nome em branco |
| **QUANDO** clicar em "Salvar" |
| **ENTÃO** deve ser exibido aviso de nome obrigatório |

| **Critérios de aceitação** |
| :------------------------- |
| Cadastro bloqueado com aviso. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Exibido o aviso "Informe o nome do exercício.". | [Print](../Evidencias/C04-CT01.png) | - |

---

### Caso de Teste 02: Cadastrar exercício com dados válidos.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT02 | O exercício deve ser incluído no grupo muscular escolhido. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário clica em "Adicionar" no grupo Peitoral |
| **E** preenche o Nome com um nome de teste |
| **QUANDO** clicar em "Salvar" |
| **ENTÃO** o exercício deve aparecer no grupo Peitoral e o total deve aumentar |

| **Critérios de aceitação** |
| :------------------------- |
| Exercício listado no grupo e contador atualizado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Exercício listado em Peitoral e total atualizado. | [Vídeo Jam](https://jam.dev/c/35d0b2b5-9ac2-4c7a-a63f-a172aeaaa7dc) | - |

---

### Caso de Teste 03: Cadastrar exercício duplicado no mesmo grupo.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT03 | O sistema não deve permitir dois exercícios com o mesmo nome no mesmo grupo. |

| **Pré-condições** |
| :---------------- |
| Exercício de teste já cadastrado (C04-CT02). |

| **Passos** |
| :--------- |
| **DADO** que já existe o exercício de teste no grupo Peitoral |
| **E** o usuário adiciona outro exercício com o mesmo nome no mesmo grupo |
| **QUANDO** clicar em "Salvar" |
| **ENTÃO** deve ser exibido aviso de exercício já cadastrado |

| **Critérios de aceitação** |
| :------------------------- |
| Duplicidade bloqueada. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | O exercício duplicado foi salvo; o grupo passou a ter 2 itens iguais. | [Vídeo Jam](https://jam.dev/c/a84d54b0-8ca9-4871-9a16-5c563024a8f4) | BUG-010 |

---

### Caso de Teste 04: Excluir exercício.

| ID       | Descrição |
| :------- | :-------- |
| C04-CT04 | O sistema deve excluir o exercício após confirmação. |

| **Pré-condições** |
| :---------------- |
| Exercício existente. |

| **Passos** |
| :--------- |
| **DADO** que o grupo Peitoral tem o exercício |
| **E** o usuário clica no "X" (Deletar) do exercício de teste |
| **QUANDO** confirmar a exclusão |
| **ENTÃO** o exercício deve ser removido e o total atualizado |

| **Critérios de aceitação** |
| :------------------------- |
| Exercício removido e total do grupo atualizado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Exercício removido e total atualizado. | [Vídeo Jam](https://jam.dev/c/77fa5e4f-a14b-41ce-9c31-e1515abaecc1) | - |

---
