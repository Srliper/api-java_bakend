# 📋 TODOS OS TESTES - CONFIGURAÇÃO EXATA

## 🎯 TESTE 1: CRIAR TAREFA (POST)

### Configuração no Postman:

**Método:** POST  
**URL:** `http://localhost:8080/api/tarefas`

**Headers:**
- Key: `Content-Type`
- Value: `application/json`

**Body (raw JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**Resultado Esperado:**
- Status: `201 Created`
- Response mostra a tarefa criada com ID

**Print:** Deve mostrar Request e Response com "Luis 4555952" visível

---

## 🎯 TESTE 2: LISTAR TODAS AS TAREFAS (GET)

### Configuração no Postman:

**Método:** GET  
**URL:** `http://localhost:8080/api/tarefas`

**Headers:** Não precisa  
**Body:** Não precisa

**Resultado Esperado:**
- Status: `200 OK`
- Response mostra array com todas as tarefas:
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

**Print:** Deve mostrar a lista com sua tarefa contendo "Luis 4555952"

---

## 🎯 TESTE 3: BUSCAR TAREFA POR ID (GET)

### Configuração no Postman:

**Método:** GET  
**URL:** `http://localhost:8080/api/tarefas/1`  
*(Use o ID da tarefa criada no Teste 1 - geralmente será 1)*

**Headers:** Não precisa  
**Body:** Não precisa

**Resultado Esperado:**
- Status: `200 OK`
- Response mostra apenas a tarefa com ID 1

**Print:** Opcional (não é obrigatório para o trabalho)

---

## 🎯 TESTE 4: ATUALIZAR TAREFA (PUT)

### Configuração no Postman:

**Método:** PUT  
**URL:** `http://localhost:8080/api/tarefas/1`  
*(Use o ID da tarefa criada - geralmente será 1)*

**Headers:**
- Key: `Content-Type`
- Value: `application/json`

**Body (raw JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**Resultado Esperado:**
- Status: `200 OK`
- Response mostra a tarefa atualizada

**Print:** Deve mostrar atualização com "Luis 4555952" visível

---

## 🎯 TESTE 5: REMOVER TAREFA (DELETE)

### Configuração no Postman:

**Método:** DELETE  
**URL:** `http://localhost:8080/api/tarefas/1`  
*(Use o ID da tarefa criada - geralmente será 1)*

**Headers:** Não precisa  
**Body:** Não precisa

**Resultado Esperado:**
- Status: `204 No Content`
- Response vazio

**Print:** Deve mostrar status 204 No Content

---

## 📸 PRINTS OBRIGATÓRIOS PARA O TRABALHO

Conforme os critérios de avaliação, você precisa de **4 prints**:

1. ✅ **Teste 1 (POST)** - Criação com "Luis 4555952"
2. ✅ **Teste 2 (GET)** - Listagem com "Luis 4555952"
3. ✅ **Teste 4 (PUT)** - Atualização com "Luis 4555952"
4. ✅ **Teste 5 (DELETE)** - Remoção (status 204)

**Teste 3 é opcional** (não é obrigatório para o trabalho)

---

## 🎯 SEQUÊNCIA RECOMENDADA

Execute nesta ordem:

1. **Teste 1 (POST)** - Criar tarefa
   - Anote o ID retornado (geralmente será 1)

2. **Teste 2 (GET)** - Listar tarefas
   - Confirme que sua tarefa aparece na lista

3. **Teste 3 (GET /{id})** - Buscar por ID (opcional)
   - Use o ID do Teste 1

4. **Teste 4 (PUT)** - Atualizar tarefa
   - Use o mesmo ID

5. **Teste 5 (DELETE)** - Remover tarefa
   - Use o mesmo ID

6. **Teste 2 novamente** - Confirmar remoção
   - Deve retornar array vazio `[]`

---

## ✅ CHECKLIST RÁPIDO

### Teste 1 (POST):
- [ ] Método: POST
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Header: `Content-Type: application/json`
- [ ] Body: JSON com "Luis 4555952"
- [ ] Status: 201 Created
- [ ] Print tirado

### Teste 2 (GET):
- [ ] Método: GET
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Status: 200 OK
- [ ] Lista mostra "Luis 4555952"
- [ ] Print tirado

### Teste 4 (PUT):
- [ ] Método: PUT
- [ ] URL: `http://localhost:8080/api/tarefas/1`
- [ ] Header: `Content-Type: application/json`
- [ ] Body: JSON com "Luis 4555952"
- [ ] Status: 200 OK
- [ ] Print tirado

### Teste 5 (DELETE):
- [ ] Método: DELETE
- [ ] URL: `http://localhost:8080/api/tarefas/1`
- [ ] Status: 204 No Content
- [ ] Print tirado

---

## 🚀 RESUMO ULTRA RÁPIDO

**Teste 1 (POST):**
- POST → `http://localhost:8080/api/tarefas`
- Body: JSON com "Luis 4555952"

**Teste 2 (GET):**
- GET → `http://localhost:8080/api/tarefas`
- Sem Body, sem Headers

**Teste 4 (PUT):**
- PUT → `http://localhost:8080/api/tarefas/1`
- Body: JSON com "Luis 4555952"

**Teste 5 (DELETE):**
- DELETE → `http://localhost:8080/api/tarefas/1`
- Sem Body, sem Headers

---

**Pronto para testar! 🎯**

