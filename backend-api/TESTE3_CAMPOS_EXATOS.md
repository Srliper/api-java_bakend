# 📝 TESTE 3: O QUE COLOCAR EM CADA CAMPO DO POSTMAN

## 🎯 TESTE 3: BUSCAR TAREFA POR ID (GET)

O Teste 3 busca uma tarefa específica pelo ID. É simples como o Teste 2, mas com ID na URL!

---

## 📋 CONFIGURAÇÃO COMPLETA - CAMPO POR CAMPO

### CAMPO 1: Método HTTP
**Onde:** Dropdown à esquerda da URL  
**O que colocar:** Selecione **GET**

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

### CAMPO 3: Headers
**Onde:** Aba "Headers"  
**O que colocar:** ❌ **NÃO precisa configurar nada!**
- Pode deixar vazio
- Ou ignorar essa aba

### CAMPO 4: Body
**Onde:** Aba "Body"  
**O que colocar:** ❌ **NÃO precisa configurar nada!**
- Pode deixar vazio
- Ou ignorar essa aba

### CAMPO 5: Send
**Onde:** Botão grande azul  
**O que fazer:** Clique em **"Send"**

---

## 🎯 VISUALIZAÇÃO COMPLETA

```
┌─────────────────────────────────────────────┐
│ [GET ▼] http://localhost:8080/api/tarefas/1 │ ← Método + URL com ID
│                                             │
│ [Params] [Headers] [Body] [Auth] [Settings]│
│                                             │
│ Headers: (vazio - não precisa)             │
│                                             │
│ Body: (vazio - não precisa)                 │
│                                             │
│                                    [Send]   │ ← Só clicar aqui!
└─────────────────────────────────────────────┘
```

---

## 📸 O QUE DEVE APARECER

### Request (Lado Esquerdo):
```
GET  http://localhost:8080/api/tarefas/1
```

### Response (Lado Direito) - Se encontrou:
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
3. Use esse ID no Teste 3

**Geralmente será `1`** se foi a primeira tarefa criada.

---

## ✅ CHECKLIST DO TESTE 3

Antes de clicar em "Send", verifique:

- [ ] Método: GET selecionado
- [ ] URL: `http://localhost:8080/api/tarefas/1` (com ID)
- [ ] ID correto (do Teste 1)
- [ ] Headers: Vazio (ok, não precisa)
- [ ] Body: Vazio (ok, não precisa)
- [ ] Clicar em Send
- [ ] Status: 200 OK (se encontrou)
- [ ] Response mostra a tarefa específica
- [ ] "Luis 4555952" está visível na resposta

---

## 🎯 COMPARAÇÃO: TESTE 2 vs TESTE 3

| Campo | Teste 2 (GET todas) | Teste 3 (GET por ID) |
|-------|---------------------|----------------------|
| Método | GET | GET |
| URL | `/api/tarefas` | `/api/tarefas/1` |
| ID na URL? | ❌ Não | ✅ Sim |
| Headers | ❌ Não precisa | ❌ Não precisa |
| Body | ❌ Não precisa | ❌ Não precisa |

**Diferença:** Teste 3 tem o ID no final da URL!

---

## 📸 COMO TIRAR O PRINT

### 1. Ajustar a Tela
- Ajuste o zoom para mostrar Request e Response juntos

### 2. Capturar
- `Windows + Shift + S` ou Snipping Tool
- Capture a tela completa do Postman

### 3. O Que Deve Aparecer no Print

✅ Método GET visível  
✅ URL: `http://localhost:8080/api/tarefas/1` (com ID)  
✅ Status: `200 OK`  
✅ Response com tarefa específica  
✅ **"Luis 4555952"** claramente visível

---

## ⚠️ OBSERVAÇÃO IMPORTANTE

**O Teste 3 NÃO é obrigatório para o trabalho!**

Conforme os critérios de avaliação, você precisa de prints de:
- ✅ Teste 1 (POST) - Criação
- ✅ Teste 2 (GET) - Listagem
- ✅ Teste 4 (PUT) - Atualização
- ✅ Teste 5 (DELETE) - Remoção

**Teste 3 é opcional**, mas é bom testar para garantir que está funcionando!

---

## 🎯 RESUMO

**Teste 3 = GET com ID na URL**

- Método: GET
- URL: `http://localhost:8080/api/tarefas/1` (com ID)
- **Só isso!** Sem Headers, sem Body
- Clique em Send
- Veja a tarefa específica
- Tire o print (opcional)

**É simples como o Teste 2, mas com ID na URL!** ✅

---

**Pronto para fazer o Teste 3! 🚀**

