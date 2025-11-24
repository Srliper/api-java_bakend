# 📸 TESTE 1: CRIAR TAREFA - GUIA COMPLETO

## 🎯 O QUE VOCÊ PRECISA FAZER

### PASSO 1: Configurar a Requisição no Postman

#### 1.1 Método HTTP
- Selecione: **POST**

#### 1.2 URL (Endpoint)
```
http://localhost:8080/api/tarefas
```

**⚠️ IMPORTANTE:**
- Certifique-se de que a aplicação Spring Boot está rodando
- A URL deve ser exatamente como mostrado acima
- Não adicione barra no final (`/api/tarefas/` ❌)

#### 1.3 Headers
- Clique na aba **"Headers"**
- Adicione:
  - **Key:** `Content-Type`
  - **Value:** `application/json`

#### 1.4 Body (Corpo da Requisição)
- Clique na aba **"Body"**
- Selecione **"raw"**
- No dropdown ao lado, selecione **"JSON"**
- Cole exatamente este JSON:

```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

---

## 📸 O QUE DEVE APARECER NO PRINT

### ✅ Print Completo do Teste 1

Seu print deve mostrar claramente:

#### Lado Esquerdo (Request):
1. ✅ Método: **POST** (visível no dropdown)
2. ✅ URL: `http://localhost:8080/api/tarefas` (visível na barra de URL)
3. ✅ Aba "Body" selecionada
4. ✅ JSON visível com:
   - `"nome": "Desenvolvimento da API"`
   - `"dataEntrega": "2025-12-12"`
   - `"responsavel": "Luis 4555952"` ⚠️ **MUITO IMPORTANTE: Seu nome e RU devem estar visíveis!**

#### Lado Direito (Response):
1. ✅ Status: **201 Created** (em verde, se possível)
2. ✅ Response body mostrando:
   ```json
   {
     "id": 1,
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```
3. ⚠️ **CRÍTICO:** O campo `"responsavel": "Luis 4555952"` DEVE estar claramente visível na resposta!

---

## 🎯 EXEMPLO VISUAL DO QUE DEVE APARECER

```
┌─────────────────────────────────────────────────────────┐
│ POST  http://localhost:8080/api/tarefas                 │
│                                                          │
│ [Params] [Authorization] [Headers] [Body] [Pre-request]│
│                                                          │
│ Body ▼ raw ▼ JSON                                       │
│ ┌─────────────────────────────────────────────────────┐ │
│ │ {                                                   │ │
│ │   "nome": "Desenvolvimento da API",                │ │
│ │   "dataEntrega": "2015-12-12",                     │ │
│ │   "responsavel": "Luis 4555952"                    │ │
│ │ }                                                   │ │
│ └─────────────────────────────────────────────────────┘ │
│                                                          │
│                                    [Send]                │
├─────────────────────────────────────────────────────────┤
│ Status: 201 Created                                      │
│ Time: 234 ms                                            │
│ Size: 123 B                                             │
│                                                          │
│ Body ▼ Pretty ▼                                         │
│ ┌─────────────────────────────────────────────────────┐ │
│ │ {                                                   │ │
│ │   "id": 1,                                          │ │
│ │   "nome": "Desenvolvimento da API",                │ │
│ │   "dataEntrega": "2025-12-12",                      │ │
│ │   "responsavel": "Luis 4555952"  ← DEVE ESTAR      │ │
│ │ }                                                   │ │
│ └─────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

---

## ✅ CHECKLIST ANTES DE TIRAR O PRINT

Antes de capturar a tela, verifique:

- [ ] Aplicação Spring Boot está rodando (sem erros no console)
- [ ] Método POST está selecionado
- [ ] URL está correta: `http://localhost:8080/api/tarefas`
- [ ] Header `Content-Type: application/json` está configurado
- [ ] Body JSON está correto com "Luis 4555952"
- [ ] Status da resposta é **201 Created** (não 200, não 400, não 500)
- [ ] Response body mostra a tarefa criada
- [ ] **"Luis 4555952" está visível no campo "responsavel" da resposta**
- [ ] Tela está completa (não cortada)
- [ ] Texto está legível

---

## ⚠️ PROBLEMAS COMUNS E SOLUÇÕES

### Problema: Status 400 Bad Request
**Causa:** JSON inválido ou campos faltando

**Solução:**
- Verifique se o JSON está correto (vírgulas, chaves)
- Certifique-se de que todos os campos estão presentes:
  - `nome`
  - `dataEntrega`
  - `responsavel`

### Problema: Status 500 Internal Server Error
**Causa:** Banco de dados não conectado ou aplicação com erro

**Solução:**
- Verifique se MySQL está rodando
- Verifique se o banco `tarefasdb` foi criado
- Veja os logs da aplicação para identificar o erro

### Problema: Connection Refused
**Causa:** Aplicação não está rodando

**Solução:**
- Inicie a aplicação Spring Boot
- Aguarde a mensagem "Started BackendApiApplication"

### Problema: Status 404 Not Found
**Causa:** URL incorreta

**Solução:**
- Verifique a URL: `http://localhost:8080/api/tarefas`
- Certifique-se de que não há barra no final
- Verifique se a aplicação está na porta 8080

---

## 📝 DADOS EXATOS PARA USAR

**Método:** POST  
**URL:** `http://localhost:8080/api/tarefas`  
**Header:** `Content-Type: application/json`  
**Body (JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**Resposta Esperada:**
- Status: **201 Created**
- Body com a tarefa criada incluindo `"responsavel": "Luis 4555952"`

---

## 🎯 PONTOS CRÍTICOS PARA A NOTA

Conforme os critérios de avaliação:

> **Teste 1 - Implementação correta do endpoint de inserção com nome e RU do aluno.**
> **Se não colocar EVIDÊNCIA (print) contendo nome e RU, receberá nota 0.**

### ✅ O QUE GARANTE A NOTA:

1. ✅ Print mostra método POST
2. ✅ Print mostra URL correta
3. ✅ Print mostra Body JSON com "Luis 4555952"
4. ✅ Print mostra Status 201 Created
5. ✅ **Print mostra Response com "Luis 4555952" no campo "responsavel"** ⚠️ CRÍTICO

---

## 💡 DICA PARA UM BOM PRINT

1. **Ajuste o zoom do Postman** para que tudo caiba na tela
2. **Use a ferramenta de screenshot do Windows:**
   - `Windows + Shift + S` para captura de tela
   - Ou use "Snipping Tool"
3. **Capture a tela completa** mostrando Request e Response
4. **Verifique se o texto está legível** antes de salvar

---

## ✅ RESUMO RÁPIDO

**O que fazer:**
1. POST → `http://localhost:8080/api/tarefas`
2. Header: `Content-Type: application/json`
3. Body: JSON com "Luis 4555952"
4. Clicar em Send
5. Verificar Status 201
6. Tirar print mostrando Request e Response

**O que deve aparecer no print:**
- ✅ Método POST
- ✅ URL correta
- ✅ JSON com "Luis 4555952"
- ✅ Status 201 Created
- ✅ **Response com "Luis 4555952" visível** ⚠️

---

**Boa sorte! 🚀**

