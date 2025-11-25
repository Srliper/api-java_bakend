# 📝 TESTE 4: O QUE COLOCAR EM CADA CAMPO DO POSTMAN

## 🎯 TESTE 4: ATUALIZAR TAREFA (PUT)

O Teste 4 atualiza uma tarefa existente. **É OBRIGATÓRIO para o trabalho!**

É similar ao Teste 1, mas usa PUT e tem ID na URL.

---

## 📋 CONFIGURAÇÃO COMPLETA - CAMPO POR CAMPO

### CAMPO 1: Método HTTP
**Onde:** Dropdown à esquerda da URL  
**O que colocar:** Selecione **PUT**

### CAMPO 2: URL (Endpoint) - COM ID!
**Onde:** Barra de URL grande  
**O que colocar:** 
```
http://localhost:8080/api/tarefas/1
```

**⚠️ IMPORTANTE:** 
- Use o ID da tarefa criada no Teste 1
- Geralmente será `1` (se foi a primeira tarefa)
- O ID vai no final da URL: `/api/tarefas/1`

### CAMPO 3: Headers (Aba "Headers")
**Onde:** Clique na aba **"Headers"** (abaixo da URL)

**O que colocar:**
- **Key:** `Content-Type`
- **Value:** `application/json`

**⚠️ IMPORTANTE:** Sem isso, a API não vai aceitar o JSON!

### CAMPO 4: Body (Aba "Body")
**Onde:** Clique na aba **"Body"** (ao lado de "Headers")

**Passos:**
1. Selecione o botão **"raw"**
2. No dropdown à direita, selecione **"JSON"**
3. Na área de texto, cole:
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**⚠️ MUITO IMPORTANTE:** Sem o Body, não tem dados para atualizar!

### CAMPO 5: Send
**Onde:** Botão grande azul  
**O que fazer:** Clique em **"Send"**

---

## 🎯 VISUALIZAÇÃO COMPLETA

```
┌─────────────────────────────────────────────┐
│ [PUT ▼] http://localhost:8080/api/tarefas/1│ ← Método + URL com ID
│                                             │
│ [Params] [Headers] [Body] [Auth] [Settings]│
│                                             │
│ Headers:                                    │
│ Key: Content-Type                           │ ← Headers
│ Value: application/json                     │
│                                             │
│ Body ▼ raw ▼ JSON                           │
│ {                                           │
│   "nome": "Desenvolvimento da API",         │
│   "dataEntrega": "2025-12-12",              │ ← Body
│   "responsavel": "Luis 4555952"            │
│ }                                           │
│                                             │
│                                    [Send]   │
└─────────────────────────────────────────────┘
```

---

## 📸 O QUE DEVE APARECER

### Request (Lado Esquerdo):
```
PUT  http://localhost:8080/api/tarefas/1

Headers:
Content-Type: application/json

Body:
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Response (Lado Direito) - Se atualizou:
```
Status: 200 OK

{
  "id": 1,
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Response (Lado Direito) - Se NÃO encontrou:
```
Status: 404 Not Found
```

---

## ⚠️ IMPORTANTE: QUAL ID USAR?

**Use o ID retornado no Teste 1!**

### Como descobrir o ID:

1. **Execute o Teste 1 (POST)** primeiro
2. Na resposta do Teste 1, veja o campo `"id"`:
   ```json
   {
     "id": 1,  ← Este é o ID!
     "nome": "Desenvolvimento da API",
     ...
   }
   ```
3. Use esse ID no Teste 4

**Geralmente será `1`** se foi a primeira tarefa criada.

---

## ✅ CHECKLIST DO TESTE 4

Antes de clicar em "Send", verifique:

- [ ] Método: PUT selecionado
- [ ] URL: `http://localhost:8080/api/tarefas/1` (com ID)
- [ ] ID correto (do Teste 1)
- [ ] Header: `Content-Type: application/json`
- [ ] Body: "raw" selecionado
- [ ] Body: "JSON" selecionado no dropdown
- [ ] Body: JSON com os 3 campos preenchidos
- [ ] "Luis 4555952" está no JSON
- [ ] Clicar em Send
- [ ] Status: 200 OK
- [ ] Response mostra tarefa atualizada
- [ ] "Luis 4555952" está visível na resposta
- [ ] **Print tirado** ⚠️ OBRIGATÓRIO!

---

## 🎯 COMPARAÇÃO: TESTE 1 vs TESTE 4

| Campo | Teste 1 (POST) | Teste 4 (PUT) |
|-------|----------------|---------------|
| Método | POST | PUT |
| URL | `/api/tarefas` | `/api/tarefas/1` |
| ID na URL? | ❌ Não (cria nova) | ✅ Sim (atualiza existente) |
| Headers | ✅ Sim | ✅ Sim |
| Body | ✅ Sim (JSON) | ✅ Sim (JSON) |

**Diferença:** Teste 4 tem ID na URL e usa PUT!

---

## 📸 COMO TIRAR O PRINT

### 1. Ajustar a Tela
- Ajuste o zoom para mostrar Request e Response juntos

### 2. Capturar
- `Windows + Shift + S` ou Snipping Tool
- Capture a tela completa do Postman

### 3. O Que Deve Aparecer no Print

✅ Método PUT visível  
✅ URL: `http://localhost:8080/api/tarefas/1` (com ID)  
✅ Header: `Content-Type: application/json`  
✅ Body JSON com "Luis 4555952"  
✅ Status: `200 OK`  
✅ Response com tarefa atualizada  
✅ **"Luis 4555952"** claramente visível no campo "responsavel"

---

## ⚠️ CRITÉRIO DE AVALIAÇÃO

Conforme os critérios do trabalho:

> **Teste 3 - Implementação correta do endpoint de atualização do registro contendo nome do aluno e RU.**
> **Se não colocar EVIDÊNCIA (print) de que atualizou o registro contendo nome do aluno e RU, receberá nota 0.**

### ✅ O QUE GARANTE A NOTA:

1. ✅ Print mostra método PUT
2. ✅ Print mostra URL com ID
3. ✅ Print mostra Body JSON com "Luis 4555952"
4. ✅ Print mostra Status 200 OK
5. ✅ **Print mostra Response com "Luis 4555952" no campo "responsavel"** ⚠️ CRÍTICO

---

## 🎯 RESUMO

**Teste 4 = PUT com ID e Body**

- Método: PUT
- URL: `http://localhost:8080/api/tarefas/1` (com ID)
- Header: `Content-Type: application/json`
- Body: JSON com "Luis 4555952"
- Clique em Send

**É OBRIGATÓRIO para o trabalho!** ⚠️

---

**Pronto para fazer o Teste 4! 🚀**

