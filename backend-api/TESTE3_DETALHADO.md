# 🔍 TESTE 3: BUSCAR TAREFA POR ID (GET)

## 🎯 TESTE 3: GET COM ID NA URL

O Teste 3 busca uma tarefa específica pelo ID.

---

## 📝 CONFIGURAÇÃO NO POSTMAN

### Passo a Passo:

1. **Crie nova requisição**

2. **Método:**
   - Selecione **GET** no dropdown

3. **URL:**
   - Digite: `http://localhost:8080/api/tarefas/1`
   - ⚠️ **IMPORTANTE:** Use o ID da tarefa criada no Teste 1
   - Geralmente será `1` (se foi a primeira tarefa criada)
   - Se criou outras antes, use o ID correto

4. **Headers:**
   - ❌ **NÃO precisa configurar nada!**

5. **Body:**
   - ❌ **NÃO precisa configurar nada!**

6. **Clique em "Send"**

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

1. Execute o **Teste 1 (POST)** primeiro
2. Na resposta, veja o campo `"id"`:
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

## 🎯 EXEMPLO COMPLETO

### Sequência de Testes:

1. **Teste 1 (POST):**
   - Cria tarefa
   - Resposta: `{"id": 1, ...}`

2. **Teste 3 (GET /{id}):**
   - URL: `http://localhost:8080/api/tarefas/1`
   - Busca a tarefa com ID 1
   - Deve retornar a mesma tarefa criada

---

## ✅ CHECKLIST DO TESTE 3

- [ ] Método: GET
- [ ] URL: `http://localhost:8080/api/tarefas/1` (ou ID correto)
- [ ] Headers: Vazio (não precisa)
- [ ] Body: Vazio (não precisa)
- [ ] Status: 200 OK (se encontrou)
- [ ] Response mostra a tarefa com o ID
- [ ] "Luis 4555952" está visível na resposta

---

## 🧪 TESTE DE ERRO (Opcional)

Você também pode testar com um ID que não existe:

**URL:** `http://localhost:8080/api/tarefas/999`

**Resultado Esperado:**
- Status: `404 Not Found`

Isso mostra que o tratamento de erro está funcionando!

---

## 📋 COMPARAÇÃO COM OUTROS TESTES

| Teste | Método | URL | ID na URL? |
|-------|--------|-----|------------|
| **Teste 1** | POST | `/api/tarefas` | ❌ Não |
| **Teste 2** | GET | `/api/tarefas` | ❌ Não |
| **Teste 3** | GET | `/api/tarefas/1` | ✅ Sim |
| **Teste 4** | PUT | `/api/tarefas/1` | ✅ Sim |
| **Teste 5** | DELETE | `/api/tarefas/1` | ✅ Sim |

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

**Teste 3 = GET com ID**

- Método: GET
- URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)
- Sem Headers
- Sem Body
- Clique em Send

**É simples como o Teste 2, mas com ID na URL!** ✅

