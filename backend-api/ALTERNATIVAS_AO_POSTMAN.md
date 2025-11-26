# 🔄 ALTERNATIVAS AO POSTMAN PARA TESTAR A API

## ⚠️ IMPORTANTE: SPRING BOOT É OBRIGATÓRIO

**NÃO podemos remover o Spring Boot Java!** O trabalho exige:
- ✅ Java com Spring Boot (OBRIGATÓRIO)
- ✅ MySQL (OBRIGATÓRIO)
- ✅ Spring Data JPA (OBRIGATÓRIO)
- ✅ Postman **ou similar** (pode usar alternativa)

---

## 🎯 POSTMAN FUNCIONA COM LOCALHOST!

**Postman FUNCIONA perfeitamente com `http://localhost:8080`!**

Não há problema em usar Postman com localhost. Se está tendo problemas, pode ser:
- Aplicação Spring Boot não está rodando
- URL incorreta
- Porta diferente

---

## 🔄 ALTERNATIVAS AO POSTMAN (Se Precisar)

### Opção 1: Thunder Client (VS Code Extension) ⭐ RECOMENDADO

**Vantagens:**
- ✅ Funciona direto no VS Code
- ✅ Não precisa instalar aplicativo separado
- ✅ Interface similar ao Postman
- ✅ Funciona com localhost
- ✅ Grátis

**Como instalar:**
1. Abra VS Code
2. Clique em **Extensions** (ícone de quadrados) ou `Ctrl+Shift+X`
3. Procure: **"Thunder Client"**
4. Clique em **Install**
5. Pronto! Aparece um ícone de raio na barra lateral

**Como usar:**
1. Clique no ícone **Thunder Client** (raio)
2. Clique em **"New Request"**
3. Configure igual ao Postman:
   - Método: POST, GET, PUT, DELETE
   - URL: `http://localhost:8080/api/tarefas`
   - Headers: `Content-Type: application/json`
   - Body: JSON

**Print:** Use `Windows + Shift + S` para capturar a tela do VS Code

---

### Opção 2: REST Client (VS Code Extension)

**Vantagens:**
- ✅ Funciona no VS Code
- ✅ Usa arquivos `.http` ou `.rest`
- ✅ Muito simples

**Como instalar:**
1. Extensions → Procure **"REST Client"**
2. Install

**Como usar:**
1. Crie arquivo `test.http` na pasta do projeto
2. Escreva as requisições:
```http
### Criar Tarefa
POST http://localhost:8080/api/tarefas
Content-Type: application/json

{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}

### Listar Tarefas
GET http://localhost:8080/api/tarefas

### Buscar Tarefa
GET http://localhost:8080/api/tarefas/1

### Atualizar Tarefa
PUT http://localhost:8080/api/tarefas/1
Content-Type: application/json

{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}

### Remover Tarefa
DELETE http://localhost:8080/api/tarefas/1
```
3. Clique em **"Send Request"** acima de cada requisição

---

### Opção 3: Insomnia

**Vantagens:**
- ✅ Similar ao Postman
- ✅ Interface moderna
- ✅ Funciona com localhost
- ✅ Grátis

**Como instalar:**
1. Acesse: https://insomnia.rest/download
2. Baixe e instale
3. Use igual ao Postman

---

### Opção 4: Postman Web (No Navegador)

**Se o problema é o aplicativo desktop:**
1. Acesse: https://web.postman.co/
2. Faça login (conta gratuita)
3. Use no navegador
4. Funciona com localhost normalmente

---

## 🎯 RECOMENDAÇÃO: THUNDER CLIENT

**Para você que usa VS Code, recomendo Thunder Client porque:**
- ✅ Tudo em um lugar só (VS Code)
- ✅ Não precisa abrir outro aplicativo
- ✅ Interface familiar
- ✅ Funciona perfeitamente com localhost
- ✅ Fácil de tirar prints

---

## 📋 COMO USAR THUNDER CLIENT (Passo a Passo)

### 1. Instalar
- Extensions → "Thunder Client" → Install

### 2. Abrir
- Clique no ícone de raio na barra lateral

### 3. Criar Requisição (Teste 1 - POST)

**a) Clique em "New Request"**

**b) Configure:**
- **Method:** Selecione **POST**
- **URL:** Digite `http://localhost:8080/api/tarefas`

**c) Headers:**
- Clique em **"Headers"**
- Key: `Content-Type`
- Value: `application/json`

**d) Body:**
- Clique em **"Body"**
- Selecione **"JSON"**
- Cole:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**e) Send:**
- Clique em **"Send"**

**f) Print:**
- `Windows + Shift + S`
- Capture a tela do VS Code mostrando Request e Response

---

## ⚠️ IMPORTANTE: O QUE NÃO PODE MUDAR

**NÃO pode remover:**
- ❌ Spring Boot Java (OBRIGATÓRIO pelo trabalho)
- ❌ MySQL (OBRIGATÓRIO)
- ❌ Spring Data JPA (OBRIGATÓRIO)

**PODE mudar:**
- ✅ Postman → Thunder Client
- ✅ Postman → REST Client
- ✅ Postman → Insomnia
- ✅ Postman → Postman Web

O trabalho diz: **"Utilizar Postman (ou similar)"** - então pode usar alternativa!

---

## 🎯 RESUMO

1. **Spring Boot DEVE continuar** (obrigatório)
2. **Postman funciona com localhost** (se quiser continuar usando)
3. **Se preferir alternativa:** Use Thunder Client no VS Code
4. **Tire prints** da ferramenta que escolher
5. **Coloque prints no caderno**

---

## 🚀 PRÓXIMOS PASSOS

1. Escolha uma ferramenta (Thunder Client recomendado)
2. Instale no VS Code
3. Teste os 5 endpoints
4. Tire prints
5. Coloque no caderno

**Pronto! 🎉**

