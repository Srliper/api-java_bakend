# 📝 TESTE 1: O QUE COLOCAR EM CADA CAMPO DO POSTMAN

## 🎯 NÃO É SÓ POST + LINK!

Você precisa configurar **4 coisas** no Postman:

1. ✅ Método: POST
2. ✅ URL: `http://localhost:8080/api/tarefas`
3. ✅ **Headers** (importante!)
4. ✅ **Body** (muito importante!)

---

## 📋 CONFIGURAÇÃO COMPLETA - CAMPO POR CAMPO

### CAMPO 1: Método HTTP
**Onde:** Dropdown à esquerda da URL  
**O que colocar:** Selecione **POST**

### CAMPO 2: URL (Endpoint)
**Onde:** Barra de URL grande  
**O que colocar:** 
```
http://localhost:8080/api/tarefas
```

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

**⚠️ MUITO IMPORTANTE:** Sem o Body, não tem dados para criar a tarefa!

---

## 🎯 VISUALIZAÇÃO COMPLETA

```
┌─────────────────────────────────────────────┐
│ [POST ▼] http://localhost:8080/api/tarefas │ ← Método + URL
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

## ⚠️ O QUE ACONTECE SE ESQUECER ALGO

### Se esquecer Headers:
- ❌ Status: 400 Bad Request
- ❌ API não aceita o JSON

### Se esquecer Body:
- ❌ Status: 400 Bad Request
- ❌ Não tem dados para criar a tarefa

### Se esquecer URL:
- ❌ Erro de conexão
- ❌ Não encontra o endpoint

**Todos os 4 campos são obrigatórios!** ✅

---

## ✅ CHECKLIST COMPLETO

Antes de clicar em "Send", verifique:

- [ ] Método: POST selecionado
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Headers: `Content-Type: application/json`
- [ ] Body: "raw" selecionado
- [ ] Body: "JSON" selecionado no dropdown
- [ ] Body: JSON com os 3 campos preenchidos
- [ ] "Luis 4555952" está no JSON

---

## 🎯 RESUMO

**NÃO é só POST + link!**

Você precisa de:
1. ✅ POST (método)
2. ✅ URL: `http://localhost:8080/api/tarefas`
3. ✅ **Headers:** `Content-Type: application/json`
4. ✅ **Body:** JSON com os dados

**Todos os 4 são obrigatórios!** ⚠️

---

**Configure todos os 4 campos antes de clicar Send! 🚀**

