## Cenário 08: Check-in.

### Caso de Teste 01: Check-in com código em branco.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT01 | O sistema deve avisar que o código é obrigatório. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário acessa Check-in |
| **E** deixa o campo "Código do cliente" vazio |
| **QUANDO** clicar em "Realizar check-in" |
| **ENTÃO** deve ser exibido aviso para informar o código |

| **Critérios de aceitação** |
| :------------------------- |
| Aviso exibido. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Nenhuma mensagem ou reação da tela. | [Vídeo Jam](https://jam.dev/c/569cdd92-c448-4afe-bcc1-cd034d787e0a) | BUG-015 |

---

### Caso de Teste 02: Check-in com código inexistente.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT02 | O sistema deve informar que o cliente não existe. |

| **Pré-condições** |
| :---------------- |
| Usuário logado. |

| **Passos** |
| :--------- |
| **DADO** que o usuário está em Check-in |
| **E** digita o código "999999" |
| **QUANDO** clicar em "Realizar check-in" |
| **ENTÃO** deve ser exibida mensagem de cliente não encontrado |

| **Critérios de aceitação** |
| :------------------------- |
| Mensagem clara exibida. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | "Não foi possível concluir – Cliente não encontrado para esta empresa.". | [Print](../Evidencias/C08-CT02.png) | - |

---

### Caso de Teste 03: Check-in de cliente com matrícula ativa.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT03 | O check-in deve ser registrado e aparecer na lista do dia. |

| **Pré-condições** |
| :---------------- |
| Cliente de teste com matrícula ativa (C06-CT02). |

| **Passos** |
| :--------- |
| **DADO** que o usuário está em Check-in |
| **E** digita o código do cliente de teste |
| **QUANDO** clicar em "Realizar check-in" |
| **ENTÃO** o cliente deve aparecer na lista e "Check-ins hoje" deve aumentar |

| **Critérios de aceitação** |
| :------------------------- |
| Registro listado e contador atualizado. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ✅ Passou | Cliente listado com o plano; "Check-ins hoje" aumentou em 1. | [Vídeo Jam](https://jam.dev/c/07ad12c0-eb05-44e7-8bb0-1c3d8e5bdf34) | - |

---

### Caso de Teste 04: Horário do check-in corresponde ao horário local.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT04 | O horário de entrada deve seguir o fuso de Brasília (UTC−3). |

| **Pré-condições** |
| :---------------- |
| Check-in realizado (C08-CT03) às 13:54 (horário local). |

| **Passos** |
| :--------- |
| **DADO** que o relógio exibido no topo da tela mostra 13:54 |
| **QUANDO** o check-in for registrado |
| **ENTÃO** a coluna Entrada deve exibir 13:54 |

| **Critérios de aceitação** |
| :------------------------- |
| Horário igual ao relógio local. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Check-in feito às 13:54, mas a coluna Entrada exibe 16:54 (+3 h; aparenta ser UTC). | [Vídeo Jam](https://jam.dev/c/26554c0c-5651-4795-968e-f46eb3ccf1ea) | BUG-016 |

---

### Caso de Teste 05: Status e "Presentes agora" após o check-in.

| ID       | Descrição |
| :------- | :-------- |
| C08-CT05 | Após o check-in, o cliente deve constar como presente. |

| **Pré-condições** |
| :---------------- |
| Check-in realizado (C08-CT03). |

| **Passos** |
| :--------- |
| **DADO** que o check-in do cliente foi registrado |
| **QUANDO** a lista for atualizada |
| **ENTÃO** o status deve indicar presença e "Presentes agora" deve ser 1 |

| **Critérios de aceitação** |
| :------------------------- |
| Cliente marcado como presente. |

| **Resultado** | **Resultado obtido** | **Evidência** | **Bug** |
| :-----------: | :------------------- | :-----------: | :-----: |
| ❌ Falhou | Status "Pendente" com botão "Registrar entrada" (embora a entrada já esteja preenchida); "Presentes agora: 0". | [Print](../Evidencias/C08-CT03.png) | BUG-017 |

---
