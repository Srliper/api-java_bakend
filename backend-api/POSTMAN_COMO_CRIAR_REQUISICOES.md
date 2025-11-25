# 🎯 POSTMAN: COMO CRIAR AS REQUISIÇÕES (PASSO A PASSO)

## ⚠️ IMPORTANTE: NÃO PRECISA IMPORTAR NADA!

**Você NÃO precisa:**
- ❌ Importar pasta
- ❌ Importar do Git
- ❌ Importar arquivo

**Você VAI:**
- ✅ Criar as requisições **manualmente** no Postman
- ✅ É simples e rápido!

---

## 🚀 PASSO A PASSO COMPLETO

### PASSO 1: Abrir Postman

1. Abra o aplicativo Postman (desktop ou web)
2. Se perguntar sobre workspace, escolha **"Blank Workspace"**

### PASSO 2: Criar uma Coleção (Opcional mas Recomendado)

1. Clique no botão **"New"** (canto superior esquerdo)
2. Selecione **"Collection"**
3. Nome: **"API de Tarefas"**
4. Clique em **"Create"**

**Por quê?** Para organizar todas as requisições em um lugar só.

### PASSO 3: Criar a Primeira Requisição (POST - Criar Tarefa)

1. **Clique no botão "+"** (ao lado de "New") OU
   - Clique com botão direito na coleção "API de Tarefas"
   - Selecione "Add Request"

2. **Dê um nome:** "Criar Tarefa"

3. **Configure a requisição:**

   **a) Método HTTP:**
   - No dropdown à esquerda, selecione **POST**

   **b) URL:**
   - Digite: `http://localhost:8080/api/tarefas`
   - ⚠️ Certifique-se de que a aplicação Spring Boot está rodando!

   **c) Headers:**
   - Clique na aba **"Headers"**
   - Na linha vazia, adicione:
     - **Key:** `Content-Type`
     - **Value:** `application/json`
   - ✅ Marque a checkbox ao lado

   **d) Body:**
   - Clique na aba **"Body"**
   - Selecione o botão **"raw"**
   - No dropdown à direita, selecione **"JSON"**
   - Cole este JSON:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

4. **Salvar:**
   - Clique em **"Save"** (canto superior direito)
   - Ou pressione `Ctrl+S`

5. **Enviar:**
   - Clique no botão grande azul **"Send"**
   - Veja a resposta abaixo!

---

### PASSO 4: Criar Segunda Requisição (GET - Listar Tarefas)

1. **Clique no "+"** novamente OU
   - Clique com botão direito na coleção → "Add Request"

2. **Nome:** "Listar Tarefas"

3. **Configure:**
   - Método: **GET**
   - URL: `http://localhost:8080/api/tarefas`
   - **Não precisa de Headers ou Body!**

4. **Salve e envie!**

---

### PASSO 5: Criar Terceira Requisição (GET - Buscar por ID)

1. **Crie nova requisição**
2. **Nome:** "Buscar Tarefa por ID"
3. **Configure:**
   - Método: **GET**
   - URL: `http://localhost:8080/api/tarefas/1`
   - (Use o ID da tarefa criada - geralmente será 1)

---

### PASSO 6: Criar Quarta Requisição (PUT - Atualizar)

1. **Crie nova requisição**
2. **Nome:** "Atualizar Tarefa"
3. **Configure:**
   - Método: **PUT**
   - URL: `http://localhost:8080/api/tarefas/1`
   - Headers: `Content-Type: application/json`
   - Body (raw JSON):
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

---

### PASSO 7: Criar Quinta Requisição (DELETE - Remover)

1. **Crie nova requisição**
2. **Nome:** "Remover Tarefa"
3. **Configure:**
   - Método: **DELETE**
   - URL: `http://localhost:8080/api/tarefas/1`
   - **Não precisa de Headers ou Body!**

---

## 📸 VISUALIZAÇÃO DA INTERFACE

```
┌─────────────────────────────────────────────┐
│ Postman                    [New] [+]         │
├─────────────────────────────────────────────┤
│ API de Tarefas (Collection)                 │
│   ├─ Criar Tarefa (POST)                    │
│   ├─ Listar Tarefas (GET)                   │
│   ├─ Buscar Tarefa por ID (GET)             │
│   ├─ Atualizar Tarefa (PUT)                 │
│   └─ Remover Tarefa (DELETE)                │
├─────────────────────────────────────────────┤
│ POST  http://localhost:8080/api/tarefas [Send]│
│ [Params] [Headers] [Body] [Auth] [Settings] │
│                                               │
│ Body ▼ raw ▼ JSON                            │
│ {                                             │
│   "nome": "Desenvolvimento da API",          │
│   "dataEntrega": "2025-12-12",               │
│   "responsavel": "Luis 4555952"              │
│ }                                             │
├─────────────────────────────────────────────┤
│ Status: 201 Created                          │
│ {                                             │
│   "id": 1,                                   │
│   "nome": "Desenvolvimento da API",          │
│   "dataEntrega": "2025-12-12",               │
│   "responsavel": "Luis 4555952"              │
│ }                                             │
└─────────────────────────────────────────────┘
```

---

## ⚠️ PROBLEMAS COMUNS

### "Could not get response"
**Causa:** Aplicação Spring Boot não está rodando

**Solução:**
1. Abra o terminal
2. Vá para a pasta do projeto: `cd backend-api`
3. Execute: `mvnw.cmd spring-boot:run`
4. Aguarde aparecer "Started BackendApiApplication"
5. Tente novamente no Postman

### "Connection refused"
**Causa:** URL incorreta ou aplicação não está rodando

**Solução:**
- Verifique a URL: `http://localhost:8080/api/tarefas`
- Certifique-se de que a aplicação está rodando

### "404 Not Found"
**Causa:** URL incorreta

**Solução:**
- Verifique se a URL está exatamente: `http://localhost:8080/api/tarefas`
- Não adicione barra no final

---

## ✅ CHECKLIST

Antes de testar, verifique:

- [ ] Postman está aberto
- [ ] Coleção "API de Tarefas" criada
- [ ] Aplicação Spring Boot está rodando
- [ ] MySQL está rodando
- [ ] Banco `tarefasdb` foi criado
- [ ] Requisições criadas manualmente

---

## 🎯 RESUMO

**NÃO importe nada!**

**Crie manualmente:**
1. Coleção "API de Tarefas"
2. 5 requisições (POST, GET, GET, PUT, DELETE)
3. Configure cada uma
4. Teste e tire os prints

**É simples assim!** 🚀

---

**Pronto para criar suas requisições!**

