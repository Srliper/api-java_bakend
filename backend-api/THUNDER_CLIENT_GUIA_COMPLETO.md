# ⚡ THUNDER CLIENT: GUIA COMPLETO PARA TESTAR A API

## 🎯 POR QUE THUNDER CLIENT?

- ✅ Funciona direto no VS Code (não precisa de aplicativo separado)
- ✅ Interface similar ao Postman
- ✅ Funciona perfeitamente com `http://localhost:8080`
- ✅ Grátis e fácil de usar
- ✅ Fácil de tirar prints

---

## 📥 PASSO 1: INSTALAR THUNDER CLIENT

### No VS Code:

1. **Abra VS Code**
2. **Clique em Extensions** (ícone de quadrados) ou pressione `Ctrl+Shift+X`
3. **Procure:** `Thunder Client`
4. **Clique em Install** (primeiro resultado, por Ranga Vadhineni)
5. **Aguarde a instalação**

### Verificar Instalação:

Após instalar, você verá um **ícone de raio** ⚡ na barra lateral esquerda do VS Code.

---

## 🚀 PASSO 2: ABRIR THUNDER CLIENT

1. **Clique no ícone de raio** ⚡ na barra lateral
2. **Ou:** `Ctrl+Shift+P` → Digite "Thunder Client" → Enter

A interface do Thunder Client abrirá no painel lateral.

---

## 📝 PASSO 3: CRIAR COLEÇÃO (Opcional mas Recomendado)

1. No Thunder Client, clique em **"Collections"** (aba superior)
2. Clique em **"New Collection"**
3. Nome: **"API de Tarefas"**
4. Clique em **"Create"**

**Por quê?** Para organizar todas as requisições.

---

## 🧪 PASSO 4: TESTE 1 - CRIAR TAREFA (POST)

### 4.1. Criar Nova Requisição

1. Clique em **"New Request"** (botão grande no topo)
2. Ou clique com botão direito na coleção → **"Add Request"**

### 4.2. Configurar Requisição

**a) Método HTTP:**
- No dropdown à esquerda, selecione **POST**

**b) URL:**
- Digite: `http://localhost:8080/api/tarefas`
- ⚠️ Certifique-se de que a aplicação Spring Boot está rodando!

**c) Headers:**
- Clique na aba **"Headers"**
- Clique em **"Add Header"**
- **Key:** `Content-Type`
- **Value:** `application/json`

**d) Body:**
- Clique na aba **"Body"**
- Selecione **"JSON"** (já vem selecionado)
- Cole este JSON:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**e) Salvar (opcional):**
- Clique em **"Save"** (canto superior direito)
- Nome: "Criar Tarefa"
- Coleção: "API de Tarefas"

**f) Enviar:**
- Clique no botão **"Send"** (grande, no topo)

### 4.3. Ver Resposta

A resposta aparecerá abaixo, mostrando:
- **Status:** `201 Created`
- **Body:** JSON com a tarefa criada (incluindo `id`)

### 4.4. Tirar Print

1. Ajuste o zoom para mostrar Request e Response
2. `Windows + Shift + S` ou Snipping Tool
3. Capture a tela completa do VS Code com Thunder Client

**O que deve aparecer no print:**
- ✅ Método POST
- ✅ URL: `http://localhost:8080/api/tarefas`
- ✅ Header: `Content-Type: application/json`
- ✅ Body JSON com "Luis 4555952"
- ✅ Status: `201 Created`
- ✅ Response com tarefa criada

---

## 🧪 PASSO 5: TESTE 2 - LISTAR TAREFAS (GET)

### 5.1. Criar Nova Requisição

1. Clique em **"New Request"**
2. Nome: "Listar Tarefas"

### 5.2. Configurar

**a) Método:** **GET**

**b) URL:** `http://localhost:8080/api/tarefas`

**c) Headers:** Não precisa (GET não precisa de Body)

**d) Body:** Não precisa

### 5.3. Enviar

- Clique em **"Send"**

### 5.4. Resposta Esperada

**Status:** `200 OK`

**Body:**
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

### 5.5. Print

Capture a tela mostrando:
- ✅ Método GET
- ✅ URL
- ✅ Status 200 OK
- ✅ Response com array contendo "Luis 4555952"

---

## 🧪 PASSO 6: TESTE 3 - BUSCAR TAREFA POR ID (GET)

### 6.1. Criar Nova Requisição

- Nome: "Buscar Tarefa por ID"

### 6.2. Configurar

**a) Método:** **GET**

**b) URL:** `http://localhost:8080/api/tarefas/1`
- ⚠️ Use o ID retornado no Teste 1 (geralmente será `1`)

**c) Headers:** Não precisa

**d) Body:** Não precisa

### 6.3. Enviar e Print

- Clique em **"Send"**
- Status: `200 OK`
- Response: JSON com a tarefa (deve mostrar "Luis 4555952")
- **Tire print**

---

## 🧪 PASSO 7: TESTE 4 - ATUALIZAR TAREFA (PUT)

### 7.1. Criar Nova Requisição

- Nome: "Atualizar Tarefa"

### 7.2. Configurar

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

### 7.3. Enviar e Print

- Clique em **"Send"**
- Status: `200 OK`
- Response: JSON com tarefa atualizada
- **Tire print**

---

## 🧪 PASSO 8: TESTE 5 - REMOVER TAREFA (DELETE)

### 8.1. Criar Nova Requisição

- Nome: "Remover Tarefa"

### 8.2. Configurar

**a) Método:** **DELETE**

**b) URL:** `http://localhost:8080/api/tarefas/1`
- ⚠️ Use o ID da tarefa

**c) Headers:** Não precisa

**d) Body:** Não precisa

### 8.3. Enviar e Print

- Clique em **"Send"**
- Status: `204 No Content` (ou `200 OK`)
- Response: Vazio (normal para DELETE)
- **Tire print**

---

## 📸 DICAS PARA PRINTS

### 1. Ajustar Visualização

- Use `Ctrl +` ou `Ctrl -` para ajustar zoom
- Certifique-se de que Request e Response estão visíveis

### 2. Capturar

- `Windows + Shift + S` (Windows 10/11)
- Ou Snipping Tool
- Capture a área do VS Code com Thunder Client

### 3. O Que Deve Aparecer

- ✅ Método HTTP visível
- ✅ URL completa
- ✅ Headers (se aplicável)
- ✅ Body (se aplicável)
- ✅ Status code
- ✅ Response body
- ✅ **"Luis 4555952"** claramente visível

---

## 🎯 COMPARAÇÃO: POSTMAN vs THUNDER CLIENT

| Recurso | Postman | Thunder Client |
|---------|---------|----------------|
| Instalação | Aplicativo separado | Extensão VS Code |
| Localhost | ✅ Funciona | ✅ Funciona |
| Interface | Completa | Similar |
| Prints | Fácil | Fácil |
| Organização | Coleções | Coleções |
| Grátis | ✅ Sim | ✅ Sim |

**Ambos funcionam perfeitamente!** Escolha o que preferir.

---

## ⚠️ IMPORTANTE

1. **Spring Boot DEVE estar rodando** antes de testar
2. **MySQL DEVE estar rodando** e banco `tarefasdb` criado
3. **Use `http://localhost:8080`** (não `https://`)
4. **Tire prints de todos os 5 testes**
5. **Coloque prints no caderno**

---

## 🚀 RESUMO

1. Instale Thunder Client no VS Code
2. Abra Thunder Client (ícone de raio)
3. Crie requisições para os 5 testes
4. Execute cada teste
5. Tire prints
6. Coloque no caderno

**Pronto! 🎉**

