# ⚡ COMO TESTAR COM THUNDER CLIENT - PASSO A PASSO

## 🎯 PRÉ-REQUISITOS

Antes de começar, certifique-se de que:

- [ ] **Spring Boot está rodando** (`mvnw.cmd spring-boot:run`)
- [ ] **MySQL está rodando** e banco `tarefasdb` criado
- [ ] **Thunder Client instalado** no VS Code

---

## 🚀 PASSO 1: ABRIR THUNDER CLIENT

1. **No VS Code**, procure o **ícone de raio** ⚡ na barra lateral esquerda
2. **Clique no ícone** ⚡
3. O Thunder Client abrirá no painel lateral

**Se não encontrar o ícone:**
- Pressione `Ctrl+Shift+P`
- Digite: "Thunder Client"
- Selecione "Thunder Client: New Request"

---

## 🧪 TESTE 1: CRIAR TAREFA (POST)

### 1.1. Criar Nova Requisição

1. No Thunder Client, clique em **"New Request"** (botão grande no topo)
2. Ou pressione `Ctrl+N`

### 1.2. Configurar Requisição

**a) Método HTTP:**
- No dropdown à esquerda, selecione **POST**

**b) URL:**
- Digite: `http://localhost:8080/api/tarefas`
- ⚠️ Certifique-se de que Spring Boot está rodando!

**c) Headers:**
- Clique na aba **"Headers"**
- Clique em **"Add Header"** ou na linha vazia
- **Key:** `Content-Type`
- **Value:** `application/json`

**d) Body:**
- Clique na aba **"Body"**
- Certifique-se de que **"JSON"** está selecionado
- Cole este JSON:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### 1.3. Enviar Requisição

1. Clique no botão **"Send"** (grande, no topo)
2. Aguarde a resposta

### 1.4. Ver Resposta

**Resposta esperada:**
- **Status:** `201 Created` (verde)
- **Body:** JSON com a tarefa criada:
```json
{
  "id": 1,
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**⚠️ IMPORTANTE:** Anote o `id` retornado (geralmente será `1`). Você vai precisar dele nos próximos testes!

### 1.5. Tirar Print do Teste 1

**Como capturar:**
1. Ajuste o zoom do VS Code para mostrar Request e Response juntos
2. Use `Windows + Shift + S` (Windows 10/11)
3. Ou use Snipping Tool
4. Capture a tela completa do VS Code mostrando:
   - ✅ Método POST
   - ✅ URL: `http://localhost:8080/api/tarefas`
   - ✅ Header: `Content-Type: application/json`
   - ✅ Body JSON com "Luis 4555952"
   - ✅ Status: `201 Created`
   - ✅ Response com tarefa criada (mostrando "Luis 4555952")

**Salve o print como:** `teste1_post.png` ou `teste1_post.jpg`

---

## 🧪 TESTE 2: LISTAR TODAS AS TAREFAS (GET)

### 2.1. Criar Nova Requisição

1. Clique em **"New Request"** novamente
2. Ou pressione `Ctrl+N`

### 2.2. Configurar Requisição

**a) Método HTTP:**
- Selecione **GET**

**b) URL:**
- Digite: `http://localhost:8080/api/tarefas`

**c) Headers:**
- **NÃO precisa** (GET não precisa de Body)

**d) Body:**
- **NÃO precisa**

### 2.3. Enviar e Ver Resposta

1. Clique em **"Send"**
2. **Resposta esperada:**
   - **Status:** `200 OK` (verde)
   - **Body:** Array JSON com todas as tarefas:
```json
[
  {
    "id": 1,
    "nome": "Desenvolvimento da API",
    "dataEntrega": "2025-12-12",
    "responsavel": "Luis 4555952"
  }
]
```

### 2.4. Tirar Print do Teste 2

Capture a tela mostrando:
- ✅ Método GET
- ✅ URL: `http://localhost:8080/api/tarefas`
- ✅ Status: `200 OK`
- ✅ Response com array contendo "Luis 4555952"

**Salve como:** `teste2_get_all.png`

---

## 🧪 TESTE 3: BUSCAR TAREFA POR ID (GET)

### 3.1. Criar Nova Requisição

- Clique em **"New Request"**

### 3.2. Configurar Requisição

**a) Método:** **GET**

**b) URL:** `http://localhost:8080/api/tarefas/1`
- ⚠️ Use o ID retornado no Teste 1 (geralmente será `1`)

**c) Headers:** Não precisa

**d) Body:** Não precisa

### 3.3. Enviar e Ver Resposta

1. Clique em **"Send"**
2. **Resposta esperada:**
   - **Status:** `200 OK`
   - **Body:** JSON com a tarefa específica:
```json
{
  "id": 1,
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### 3.4. Tirar Print do Teste 3

Capture mostrando:
- ✅ Método GET
- ✅ URL: `http://localhost:8080/api/tarefas/1` (com ID)
- ✅ Status: `200 OK`
- ✅ Response com tarefa mostrando "Luis 4555952"

**Salve como:** `teste3_get_id.png`

---

## 🧪 TESTE 4: ATUALIZAR TAREFA (PUT)

### 4.1. Criar Nova Requisição

- Clique em **"New Request"**

### 4.2. Configurar Requisição

**a) Método:** **PUT**

**b) URL:** `http://localhost:8080/api/tarefas/1`
- ⚠️ Use o ID da tarefa criada no Teste 1

**c) Headers:**
- Key: `Content-Type`
- Value: `application/json`

**d) Body:**
- Selecione **"JSON"**
- Cole:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### 4.3. Enviar e Ver Resposta

1. Clique em **"Send"**
2. **Resposta esperada:**
   - **Status:** `200 OK`
   - **Body:** JSON com tarefa atualizada:
```json
{
  "id": 1,
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### 4.4. Tirar Print do Teste 4

Capture mostrando:
- ✅ Método PUT
- ✅ URL: `http://localhost:8080/api/tarefas/1` (com ID)
- ✅ Header: `Content-Type: application/json`
- ✅ Body JSON com "Luis 4555952"
- ✅ Status: `200 OK`
- ✅ Response com tarefa atualizada mostrando "Luis 4555952"

**Salve como:** `teste4_put.png`

---

## 🧪 TESTE 5: REMOVER TAREFA (DELETE)

### 5.1. Criar Nova Requisição

- Clique em **"New Request"**

### 5.2. Configurar Requisição

**a) Método:** **DELETE**

**b) URL:** `http://localhost:8080/api/tarefas/1`
- ⚠️ Use o ID da tarefa

**c) Headers:** Não precisa

**d) Body:** Não precisa

### 5.3. Enviar e Ver Resposta

1. Clique em **"Send"**
2. **Resposta esperada:**
   - **Status:** `204 No Content` (ou `200 OK`)
   - **Body:** Vazio (normal para DELETE)

### 5.4. Tirar Print do Teste 5

Capture mostrando:
- ✅ Método DELETE
- ✅ URL: `http://localhost:8080/api/tarefas/1` (com ID)
- ✅ Status: `204 No Content` (ou `200 OK`)
- ✅ Response vazio (ou mensagem de sucesso)

**Salve como:** `teste5_delete.png`

---

## 📸 DICAS PARA TIRAR PRINTS PERFEITOS

### 1. Ajustar Visualização

**No VS Code:**
- Use `Ctrl +` para aumentar zoom
- Use `Ctrl -` para diminuir zoom
- Ajuste até Request e Response ficarem visíveis juntos

### 2. Capturar Tela

**Windows 10/11:**
- `Windows + Shift + S` (ferramenta de captura)
- Selecione a área do VS Code com Thunder Client
- Salve a imagem

**Ou:**
- Use Snipping Tool (procure no menu Iniciar)
- Capture a área desejada
- Salve

### 3. O Que Deve Aparecer no Print

**Obrigatório:**
- ✅ Método HTTP visível
- ✅ URL completa
- ✅ Headers (se aplicável)
- ✅ Body (se aplicável)
- ✅ Status code (201, 200, 204, etc.)
- ✅ Response body
- ✅ **"Luis 4555952"** claramente visível

**⚠️ CRÍTICO:** O print DEVE mostrar "Luis 4555952" no campo "responsavel" da resposta!

---

## 🎯 CHECKLIST COMPLETO

Antes de considerar os testes concluídos:

### Teste 1 (POST):
- [ ] Status: 201 Created
- [ ] Response mostra tarefa criada
- [ ] "Luis 4555952" visível no print
- [ ] Print salvo

### Teste 2 (GET - Listar):
- [ ] Status: 200 OK
- [ ] Response mostra array com tarefas
- [ ] "Luis 4555952" visível no print
- [ ] Print salvo

### Teste 3 (GET - Por ID):
- [ ] Status: 200 OK
- [ ] Response mostra tarefa específica
- [ ] "Luis 4555952" visível no print
- [ ] Print salvo

### Teste 4 (PUT):
- [ ] Status: 200 OK
- [ ] Response mostra tarefa atualizada
- [ ] "Luis 4555952" visível no print
- [ ] Print salvo

### Teste 5 (DELETE):
- [ ] Status: 204 No Content (ou 200 OK)
- [ ] Tarefa removida
- [ ] Print salvo

---

## 📋 PRÓXIMOS PASSOS

Após tirar todos os prints:

1. **Salvar prints** em uma pasta (ex: `prints_postman/`)
2. **Abrir o caderno** (`CADERNO_ATIVIDADES_E_RESPOSTAS.md`)
3. **Inserir os prints** nas seções correspondentes:
   - Teste 1 → Seção "TESTE 1"
   - Teste 2 → Seção "TESTE 2"
   - Teste 3 → Seção "TESTE 3"
   - Teste 4 → Seção "TESTE 4"
   - Teste 5 → Seção "TESTE 5"

---

## ⚠️ PROBLEMAS COMUNS

### Erro: "Connection refused" ou "ECONNREFUSED"

**Causa:** Spring Boot não está rodando

**Solução:**
1. Abra terminal na pasta `backend-api`
2. Execute: `mvnw.cmd spring-boot:run`
3. Aguarde: "Started BackendApiApplication"
4. Tente novamente no Thunder Client

---

### Erro: "404 Not Found"

**Causa:** URL incorreta ou endpoint não existe

**Solução:**
- Verifique a URL: `http://localhost:8080/api/tarefas`
- Certifique-se de que Spring Boot está rodando
- Verifique se a porta é 8080

---

### Erro: "400 Bad Request"

**Causa:** JSON inválido ou campos faltando

**Solução:**
- Verifique se o JSON está correto
- Certifique-se de que tem os 3 campos: `nome`, `dataEntrega`, `responsavel`
- Verifique se `Content-Type: application/json` está nos Headers

---

## 🚀 RESUMO RÁPIDO

1. ✅ Abrir Thunder Client (ícone ⚡)
2. ✅ Criar requisição (New Request)
3. ✅ Configurar: Método, URL, Headers, Body
4. ✅ Send
5. ✅ Ver resposta
6. ✅ Tirar print (`Windows + Shift + S`)
7. ✅ Salvar print
8. ✅ Repetir para os 5 testes

**Pronto! 🎉**

---

## 📞 PRECISA DE AJUDA?

Se tiver problemas:
1. Verifique se Spring Boot está rodando
2. Verifique se MySQL está rodando
3. Verifique se a URL está correta
4. Verifique se o JSON está correto

**Thunder Client funciona perfeitamente!** ✅

