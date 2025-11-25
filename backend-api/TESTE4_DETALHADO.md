# ✏️ TESTE 4: ATUALIZAR TAREFA (PUT)

## 🎯 TESTE 4: ATUALIZAR TAREFA

O Teste 4 atualiza uma tarefa existente. **É OBRIGATÓRIO para o trabalho!**

---

## 📝 CONFIGURAÇÃO NO POSTMAN

### Passo a Passo:

1. **Crie nova requisição**

2. **Método:**
   - Selecione **PUT** no dropdown

3. **URL:**
   - Digite: `http://localhost:8080/api/tarefas/1`
   - ⚠️ **IMPORTANTE:** Use o ID da tarefa criada no Teste 1
   - Geralmente será `1` (se foi a primeira tarefa criada)

4. **Headers:**
   - Clique na aba **"Headers"**
   - Key: `Content-Type`
   - Value: `application/json`
   - ✅ Marque a checkbox

5. **Body:**
   - Clique na aba **"Body"**
   - Selecione **"raw"**
   - No dropdown, selecione **"JSON"**
   - Cole este JSON:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

6. **Clique em "Send"**

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

1. Execute o **Teste 1 (POST)** primeiro
2. Na resposta, veja o campo `"id"`:
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

## 🎯 EXEMPLO COMPLETO

### Sequência de Testes:

1. **Teste 1 (POST):**
   - Cria tarefa
   - Resposta: `{"id": 1, ...}`

2. **Teste 4 (PUT):**
   - URL: `http://localhost:8080/api/tarefas/1`
   - Body: JSON com dados atualizados
   - Atualiza a tarefa com ID 1
   - Deve retornar a tarefa atualizada

3. **Teste 2 (GET) novamente:**
   - Para confirmar que a atualização funcionou
   - Deve mostrar a tarefa com os dados atualizados

---

## ✅ CHECKLIST DO TESTE 4

- [ ] Método: PUT
- [ ] URL: `http://localhost:8080/api/tarefas/1` (ou ID correto)
- [ ] Header: `Content-Type: application/json`
- [ ] Body: JSON com "Luis 4555952"
- [ ] Status: 200 OK
- [ ] Response mostra tarefa atualizada
- [ ] "Luis 4555952" está visível na resposta
- [ ] **Print tirado** ⚠️ OBRIGATÓRIO!

---

## 📋 COMPARAÇÃO COM OUTROS TESTES

| Teste | Método | URL | Headers? | Body? |
|-------|--------|-----|----------|-------|
| **Teste 1** | POST | `/api/tarefas` | ✅ Sim | ✅ Sim |
| **Teste 2** | GET | `/api/tarefas` | ❌ Não | ❌ Não |
| **Teste 3** | GET | `/api/tarefas/1` | ❌ Não | ❌ Não |
| **Teste 4** | PUT | `/api/tarefas/1` | ✅ Sim | ✅ Sim |
| **Teste 5** | DELETE | `/api/tarefas/1` | ❌ Não | ❌ Não |

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

## 💡 DICA

Você pode alterar algum dado no JSON para ver a atualização funcionando:

```json
{
  "nome": "Desenvolvimento da API - Atualizado",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

Mas o importante é que **"Luis 4555952"** esteja visível no print!

---

## 🎯 RESUMO

**Teste 4 = PUT com ID e Body**

- Método: PUT
- URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)
- Header: `Content-Type: application/json`
- Body: JSON com "Luis 4555952"
- Clique em Send

**É OBRIGATÓRIO para o trabalho!** ⚠️

---

**Pronto para atualizar! ✏️**

