# 📸 TESTE 1: PASSO A PASSO VISUAL - O QUE COLOCAR

## 🎯 TESTE 1: CRIAR TAREFA (POST)

Este guia mostra **EXATAMENTE** o que você precisa colocar no Postman para o Teste 1.

---

## ✅ PRÉ-REQUISITOS

Antes de começar, certifique-se de que:
- [ ] MySQL está rodando
- [ ] Banco `tarefasdb` foi criado
- [ ] Aplicação Spring Boot está rodando (terminal aberto com `mvnw.cmd spring-boot:run`)

---

## 📝 PASSO A PASSO NO POSTMAN

### PASSO 1: Criar Nova Requisição

1. Abra o **Postman**
2. Clique no botão **"+"** (criar nova requisição)
   - Ou: Clique em **"New"** → **"HTTP Request"**

### PASSO 2: Configurar o Método

1. No **dropdown à esquerda**, selecione: **POST**
   - Por padrão vem "GET", mude para "POST"

### PASSO 3: Colocar a URL (Endpoint)

1. Na **barra de URL**, digite exatamente:
```
http://localhost:8080/api/tarefas
```

**⚠️ IMPORTANTE:**
- Não adicione barra no final (`/api/tarefas/` ❌)
- Use `http://` (não `https://`)
- Porta `8080` (padrão do Spring Boot)

### PASSO 4: Configurar Headers

1. Clique na aba **"Headers"** (abaixo da URL)

2. Na linha vazia, preencha:
   - **Key:** `Content-Type`
   - **Value:** `application/json`

3. ✅ **Marque a checkbox** ao lado (se houver)

**Resultado:** Deve aparecer:
```
Content-Type | application/json
```

### PASSO 5: Configurar Body

1. Clique na aba **"Body"** (ao lado de "Headers")

2. Selecione o botão **"raw"** (não "none", não "form-data", não "x-www-form-urlencoded")

3. No **dropdown à direita** (ao lado de "raw"), selecione: **"JSON"**

4. Na **área de texto grande**, cole exatamente este JSON:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**⚠️ CUIDADO:**
- Use aspas duplas `"` (não aspas simples)
- Vírgulas entre os campos
- Último campo sem vírgula
- Chaves `{ }` no início e fim

### PASSO 6: Enviar a Requisição

1. Clique no botão grande azul **"Send"** (canto superior direito)

2. **Aguarde a resposta** (aparece abaixo)

---

## 📸 O QUE DEVE APARECER

### Lado Esquerdo (Request):
```
POST  http://localhost:8080/api/tarefas

Headers:
Content-Type: application/json

Body:
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Lado Direito (Response):
```
Status: 201 Created
Time: 234 ms
Size: 123 B

Body:
{
  "id": 1,
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

---

## 📸 COMO TIRAR O PRINT

### 1. Ajustar a Tela

- Ajuste o zoom do Postman para que **Request e Response** apareçam juntos
- Use `Ctrl + Scroll` para ajustar zoom

### 2. Capturar a Tela

**Opção 1: Windows**
- Pressione `Windows + Shift + S`
- Selecione a área do Postman
- Salve a captura

**Opção 2: Snipping Tool**
- Abra "Snipping Tool" (procure no menu Iniciar)
- Clique em "New"
- Selecione a área do Postman
- Salve como imagem

### 3. O Que Deve Aparecer no Print

✅ **Método POST** visível  
✅ **URL:** `http://localhost:8080/api/tarefas`  
✅ **Body JSON** com "Luis 4555952" visível  
✅ **Status:** `201 Created`  
✅ **Response** mostrando a tarefa criada  
✅ **"Luis 4555952"** claramente visível no campo "responsavel" da resposta

---

## ⚠️ PROBLEMAS COMUNS

### Erro: "Could not get response"
**Causa:** Aplicação Spring Boot não está rodando

**Solução:**
1. Abra terminal
2. Execute: `mvnw.cmd spring-boot:run`
3. Aguarde iniciar
4. Tente novamente no Postman

### Erro: Status 400 Bad Request
**Causa:** JSON inválido

**Solução:**
- Verifique se está usando aspas duplas `"`
- Verifique se todas as vírgulas estão corretas
- Verifique se não há vírgula no último campo

### Erro: Status 500 Internal Server Error
**Causa:** Banco de dados não conectado

**Solução:**
- Verifique se MySQL está rodando
- Verifique se banco `tarefasdb` foi criado
- Verifique a senha no `application.properties`

### Erro: Connection Refused
**Causa:** URL incorreta ou aplicação não está rodando

**Solução:**
- Verifique a URL: `http://localhost:8080/api/tarefas`
- Certifique-se de que a aplicação está rodando

---

## ✅ CHECKLIST DO TESTE 1

Antes de tirar o print, verifique:

- [ ] Método: POST selecionado
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Header: `Content-Type: application/json`
- [ ] Body: JSON com "Luis 4555952"
- [ ] Status: 201 Created
- [ ] Response mostra tarefa criada
- [ ] "Luis 4555952" está visível na resposta
- [ ] Tela ajustada para captura
- [ ] Print tirado e salvo

---

## 🎯 RESUMO ULTRA RÁPIDO

**O que colocar no Postman:**

1. **Método:** POST
2. **URL:** `http://localhost:8080/api/tarefas`
3. **Headers:** `Content-Type: application/json`
4. **Body (raw JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```
5. **Clicar em Send**
6. **Tirar print** mostrando tudo

---

## 📸 EXEMPLO VISUAL DO PRINT

O print deve mostrar algo assim:

```
┌─────────────────────────────────────────────┐
│ POST  http://localhost:8080/api/tarefas [Send]│
│ [Params] [Headers] [Body] [Auth]            │
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
│   "responsavel": "Luis 4555952"  ← DEVE ESTAR│
│ }                                             │
└─────────────────────────────────────────────┘
```

---

**Pronto para fazer o Teste 1! 🚀**

