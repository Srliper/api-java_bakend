# 📝 TESTE 2: O QUE COLOCAR EM CADA CAMPO DO POSTMAN

## 🎯 TESTE 2: LISTAR TAREFAS (GET)

O Teste 2 é o **mais simples**! Só precisa de 2 coisas:

1. ✅ Método: GET
2. ✅ URL: `http://localhost:8080/api/tarefas`

**NÃO precisa de Headers!**  
**NÃO precisa de Body!**

---

## 📋 CONFIGURAÇÃO COMPLETA - CAMPO POR CAMPO

### CAMPO 1: Método HTTP
**Onde:** Dropdown à esquerda da URL  
**O que colocar:** Selecione **GET**

### CAMPO 2: URL (Endpoint)
**Onde:** Barra de URL grande  
**O que colocar:** 
```
http://localhost:8080/api/tarefas
```

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

**Pronto!** ✅

---

## 🎯 VISUALIZAÇÃO COMPLETA

```
┌─────────────────────────────────────────────┐
│ [GET ▼] http://localhost:8080/api/tarefas  │ ← Método + URL
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
GET  http://localhost:8080/api/tarefas
```

### Response (Lado Direito):
```
Status: 200 OK

[
  {
    "id": 1,
    "nome": "Desenvolvimento da API",
    "dataEntrega": "2025-12-12",
    "responsavel": "Luis 4555952"
  }
]
```

---

## ✅ CHECKLIST DO TESTE 2

Antes de clicar em "Send", verifique:

- [ ] Método: GET selecionado
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Headers: Vazio (ok, não precisa)
- [ ] Body: Vazio (ok, não precisa)
- [ ] Clicar em Send
- [ ] Status: 200 OK
- [ ] Response mostra array com tarefas
- [ ] "Luis 4555952" está visível na lista

---

## ⚠️ IMPORTANTE

**Execute o Teste 1 (POST) ANTES do Teste 2!**

Por quê?
- O Teste 1 cria a tarefa
- O Teste 2 lista as tarefas
- Se não criar antes, a lista vai estar vazia `[]`

**Sequência correta:**
1. Teste 1 (POST) - Criar tarefa
2. Teste 2 (GET) - Listar tarefas (vai mostrar a tarefa criada)

---

## 🎯 COMPARAÇÃO: TESTE 1 vs TESTE 2

| Campo | Teste 1 (POST) | Teste 2 (GET) |
|-------|----------------|---------------|
| Método | POST | GET |
| URL | `/api/tarefas` | `/api/tarefas` |
| Headers | ✅ Sim (`Content-Type`) | ❌ Não precisa |
| Body | ✅ Sim (JSON) | ❌ Não precisa |

**Teste 2 é muito mais simples!** ✅

---

## 📸 COMO TIRAR O PRINT

### 1. Ajustar a Tela
- Ajuste o zoom para mostrar Request e Response juntos

### 2. Capturar
- `Windows + Shift + S` ou Snipping Tool
- Capture a tela completa do Postman

### 3. O Que Deve Aparecer no Print

✅ Método GET visível  
✅ URL: `http://localhost:8080/api/tarefas`  
✅ Status: `200 OK`  
✅ Response com array JSON  
✅ **"Luis 4555952"** claramente visível no array

---

## 🎯 RESUMO

**Teste 2 = GET simples**

- Método: GET
- URL: `http://localhost:8080/api/tarefas`
- **Só isso!** Sem Headers, sem Body
- Clique em Send
- Veja a lista
- Tire o print

**É o teste mais fácil!** 🎉

---

**Pronto para fazer o Teste 2! 🚀**

