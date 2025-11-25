# 🗑️ TESTE 5: REMOVER TAREFA (DELETE) - EXPLICAÇÃO COMPLETA

## 🎯 SIM, O TESTE 5 REMOVE O CADASTRO!

No Teste 5 (DELETE), a tarefa é **permanentemente removida** do banco de dados.

---

## 💡 O QUE ACONTECE NO TESTE 5?

### Antes do DELETE:
- Tarefa existe no banco de dados
- ID: 1
- Nome: "Desenvolvimento da API"
- Responsável: "Luis 4555952"

### Depois do DELETE:
- ❌ Tarefa **NÃO existe mais** no banco
- ❌ Se tentar buscar por ID 1, retorna 404 Not Found
- ❌ Se listar todas, a tarefa não aparece mais

**A tarefa foi DELETADA permanentemente!** 🗑️

---

## 📝 CONFIGURAÇÃO NO POSTMAN

### Passo a Passo:

1. **Crie nova requisição**

2. **Método:**
   - Selecione **DELETE** no dropdown

3. **URL:**
   - Digite: `http://localhost:8080/api/tarefas/1`
   - ⚠️ **IMPORTANTE:** Use o ID da tarefa que quer remover
   - Geralmente será `1` (da tarefa criada no Teste 1)

4. **Headers:**
   - ❌ **NÃO precisa configurar nada!**

5. **Body:**
   - ❌ **NÃO precisa configurar nada!**

6. **Clique em "Send"**

---

## 📸 O QUE DEVE APARECER

### Request (Lado Esquerdo):
```
DELETE  http://localhost:8080/api/tarefas/1
```

### Response (Lado Direito) - Se removeu:
```
Status: 204 No Content

(Response body vazio)
```

### Response (Lado Direito) - Se NÃO encontrou:
```
Status: 404 Not Found
```

---

## ✅ VERIFICAÇÃO: CONFIRMAR QUE FOI REMOVIDO

Após executar o DELETE, você pode confirmar que a tarefa foi removida:

### Teste 1: Listar Todas (GET)
- URL: `http://localhost:8080/api/tarefas`
- Resultado: Array vazio `[]`
- ✅ Confirma que não há mais tarefas

### Teste 2: Buscar por ID (GET)
- URL: `http://localhost:8080/api/tarefas/1`
- Resultado: `404 Not Found`
- ✅ Confirma que a tarefa não existe mais

---

## 🎯 SEQUÊNCIA COMPLETA DE TESTES

Para testar tudo do início ao fim:

1. **Teste 1 (POST):** Criar tarefa
   - Cria tarefa com ID 1
   - ✅ Tarefa existe

2. **Teste 2 (GET):** Listar todas
   - Mostra array com 1 tarefa
   - ✅ Tarefa aparece na lista

3. **Teste 4 (PUT):** Atualizar tarefa
   - Atualiza a tarefa com ID 1
   - ✅ Tarefa ainda existe (atualizada)

4. **Teste 5 (DELETE):** Remover tarefa
   - Remove a tarefa com ID 1
   - ❌ Tarefa não existe mais

5. **Teste 2 (GET) novamente:** Confirmar remoção
   - Mostra array vazio `[]`
   - ✅ Confirma que foi removida

---

## ⚠️ IMPORTANTE: QUAL ID USAR?

**Use o ID da tarefa que você quer remover!**

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
3. Use esse ID no Teste 5

**Geralmente será `1`** se foi a primeira tarefa criada.

---

## ✅ CHECKLIST DO TESTE 5

- [ ] Método: DELETE
- [ ] URL: `http://localhost:8080/api/tarefas/1` (ou ID correto)
- [ ] Headers: Vazio (não precisa)
- [ ] Body: Vazio (não precisa)
- [ ] Status: 204 No Content
- [ ] Response vazio (ou "No Content")
- [ ] **Print tirado** ⚠️ OBRIGATÓRIO!

---

## 📋 COMPARAÇÃO COM OUTROS TESTES

| Teste | Método | Ação | Tarefa Existe Depois? |
|-------|--------|------|----------------------|
| **Teste 1** | POST | Criar | ✅ Sim (nova) |
| **Teste 2** | GET | Listar | ✅ Sim (não altera) |
| **Teste 3** | GET | Buscar | ✅ Sim (não altera) |
| **Teste 4** | PUT | Atualizar | ✅ Sim (atualizada) |
| **Teste 5** | DELETE | Remover | ❌ Não (deletada) |

---

## ⚠️ CRITÉRIO DE AVALIAÇÃO

Conforme os critérios do trabalho:

> **Teste 4 - Implementação correta do endpoint de remoção do registro contendo nome e RU do aluno.**
> **Se não colocar EVIDÊNCIA (print) de que removeu o registro contendo nome do aluno e RU, receberá nota 0.**

### ✅ O QUE GARANTE A NOTA:

1. ✅ Print mostra método DELETE
2. ✅ Print mostra URL com ID da tarefa que contém "Luis 4555952"
3. ✅ Print mostra Status 204 No Content
4. ✅ Print mostra que a tarefa foi removida

**⚠️ IMPORTANTE:** 
- A tarefa que você remove deve ser a que contém "Luis 4555952"
- O print deve mostrar claramente o status 204

---

## 💡 DICA: TESTE COMPLETO

Para garantir que tudo funciona:

1. **Crie uma tarefa** (Teste 1)
   - Anote o ID retornado

2. **Liste todas** (Teste 2)
   - Confirme que sua tarefa aparece

3. **Remova a tarefa** (Teste 5)
   - Use o ID anotado

4. **Liste todas novamente** (Teste 2)
   - Deve retornar array vazio `[]`
   - ✅ Confirma que foi removida!

---

## 🎯 RESUMO

**Teste 5 = DELETE remove permanentemente**

- Método: DELETE
- URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)
- Sem Headers
- Sem Body
- Status: 204 No Content
- **A tarefa é DELETADA do banco!** 🗑️

**É OBRIGATÓRIO para o trabalho!** ⚠️

---

## ⚠️ ATENÇÃO

**Depois do DELETE:**
- ❌ A tarefa não existe mais
- ❌ Não pode ser recuperada
- ❌ Se precisar testar novamente, crie uma nova tarefa (Teste 1)

**Por isso, faça o DELETE por último!** ✅

---

**Pronto para remover! 🗑️**

