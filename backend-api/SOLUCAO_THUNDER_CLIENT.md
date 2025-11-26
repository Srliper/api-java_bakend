# ⚡ SOLUÇÃO: USAR THUNDER CLIENT NO VS CODE

## 🎯 RESPOSTA RÁPIDA

**NÃO precisa remover Spring Boot!** Ele é obrigatório pelo trabalho.

**PODE usar Thunder Client** no VS Code ao invés do Postman!

---

## ✅ O QUE FAZER

### 1. Manter Spring Boot (OBRIGATÓRIO)
- ✅ Spring Boot Java DEVE continuar
- ✅ MySQL DEVE continuar
- ✅ Tudo que já está feito DEVE continuar

### 2. Usar Thunder Client (Alternativa ao Postman)
- ✅ Instalar extensão no VS Code
- ✅ Testar API direto no VS Code
- ✅ Funciona com `http://localhost:8080`
- ✅ Fácil de tirar prints

---

## 📥 INSTALAR THUNDER CLIENT (2 MINUTOS)

### Passo 1: Abrir Extensions
1. No VS Code, clique no ícone de **quadrados** na barra lateral
2. Ou pressione `Ctrl+Shift+X`

### Passo 2: Instalar
1. Procure: **"Thunder Client"**
2. Clique em **Install** (primeiro resultado)
3. Aguarde instalação

### Passo 3: Abrir
1. Aparece um **ícone de raio** ⚡ na barra lateral
2. Clique nele
3. Pronto! Thunder Client aberto

---

## 🧪 TESTE 1: CRIAR TAREFA (POST)

### No Thunder Client:

1. **Clique em "New Request"**

2. **Configure:**
   - **Method:** POST
   - **URL:** `http://localhost:8080/api/tarefas`

3. **Headers:**
   - Clique em "Headers"
   - Key: `Content-Type`
   - Value: `application/json`

4. **Body:**
   - Clique em "Body"
   - Selecione "JSON"
   - Cole:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

5. **Send:**
   - Clique em "Send"
   - Veja resposta: Status 201, tarefa criada

6. **Print:**
   - `Windows + Shift + S`
   - Capture tela do VS Code

---

## 🧪 TESTE 2: LISTAR TAREFAS (GET)

1. **New Request**
2. **Method:** GET
3. **URL:** `http://localhost:8080/api/tarefas`
4. **Send**
5. **Print**

---

## 🧪 TESTE 3: BUSCAR POR ID (GET)

1. **New Request**
2. **Method:** GET
3. **URL:** `http://localhost:8080/api/tarefas/1`
4. **Send**
5. **Print**

---

## 🧪 TESTE 4: ATUALIZAR (PUT)

1. **New Request**
2. **Method:** PUT
3. **URL:** `http://localhost:8080/api/tarefas/1`
4. **Headers:** `Content-Type: application/json`
5. **Body:** JSON com "Luis 4555952"
6. **Send**
7. **Print**

---

## 🧪 TESTE 5: REMOVER (DELETE)

1. **New Request**
2. **Method:** DELETE
3. **URL:** `http://localhost:8080/api/tarefas/1`
4. **Send**
5. **Print**

---

## ⚠️ IMPORTANTE

### O QUE NÃO PODE MUDAR:
- ❌ Spring Boot Java (OBRIGATÓRIO)
- ❌ MySQL (OBRIGATÓRIO)
- ❌ Spring Data JPA (OBRIGATÓRIO)

### O QUE PODE MUDAR:
- ✅ Postman → Thunder Client ✅
- ✅ Postman → REST Client ✅
- ✅ Postman → Insomnia ✅

**O trabalho diz: "Postman (ou similar)"** - então pode usar alternativa!

---

## 🎯 VANTAGENS DO THUNDER CLIENT

- ✅ Tudo no VS Code (não precisa abrir outro app)
- ✅ Funciona com localhost
- ✅ Interface similar ao Postman
- ✅ Fácil de tirar prints
- ✅ Grátis

---

## 🚀 RESUMO

1. ✅ **Mantenha Spring Boot** (não remova!)
2. ✅ **Instale Thunder Client** no VS Code
3. ✅ **Teste os 5 endpoints**
4. ✅ **Tire prints**
5. ✅ **Coloque no caderno**

**Pronto! 🎉**

---

## 📞 PRECISA DE AJUDA?

Se tiver problemas:
1. Certifique-se de que Spring Boot está rodando
2. Certifique-se de que MySQL está rodando
3. Use URL: `http://localhost:8080/api/tarefas`
4. Verifique se porta 8080 está livre

**Thunder Client funciona perfeitamente com localhost!** ✅

