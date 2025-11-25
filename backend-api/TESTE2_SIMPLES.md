# ✅ TESTE 2: LISTAR TAREFAS - É SÓ GET!

## 🎯 SIM, É SÓ GET!

O Teste 2 é o **mais simples** de todos:

- ✅ Método: **GET**
- ✅ URL: `http://localhost:8080/api/tarefas`
- ✅ **Sem Headers**
- ✅ **Sem Body**
- ✅ **Só clicar em Send!**

---

## 📝 CONFIGURAÇÃO NO POSTMAN

### Passo a Passo:

1. **Crie nova requisição** (ou use uma existente)

2. **Método:**
   - Selecione **GET** no dropdown

3. **URL:**
   - Digite: `http://localhost:8080/api/tarefas`
   - ⚠️ Não adicione barra no final!

4. **Headers:**
   - ❌ **NÃO precisa configurar nada!**
   - Pode deixar vazio ou ignorar essa aba

5. **Body:**
   - ❌ **NÃO precisa configurar nada!**
   - Pode deixar vazio ou ignorar essa aba

6. **Clique em "Send"**

7. **Pronto!** ✅

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

- [ ] Método: GET
- [ ] URL: `http://localhost:8080/api/tarefas`
- [ ] Headers: Vazio (não precisa)
- [ ] Body: Vazio (não precisa)
- [ ] Status: 200 OK
- [ ] Response mostra array com sua tarefa
- [ ] "Luis 4555952" está visível na resposta
- [ ] Print tirado

---

## 🎯 COMPARAÇÃO RÁPIDA

| Teste | Método | Headers? | Body? |
|-------|--------|----------|-------|
| **Teste 1** | POST | ✅ Sim | ✅ Sim (JSON) |
| **Teste 2** | GET | ❌ Não | ❌ Não |
| **Teste 4** | PUT | ✅ Sim | ✅ Sim (JSON) |
| **Teste 5** | DELETE | ❌ Não | ❌ Não |

---

## 💡 DICA

O Teste 2 é tão simples que você pode até testar no **navegador**:

1. Abra o navegador
2. Digite: `http://localhost:8080/api/tarefas`
3. Pressione Enter
4. Deve mostrar o JSON das tarefas

Mas para o trabalho, use o Postman para tirar o print! 📸

---

## ✅ RESUMO

**Teste 2 = GET simples**

- Método: GET
- URL: `http://localhost:8080/api/tarefas`
- **Só isso!** Sem Headers, sem Body
- Clique em Send e pronto!

**É o teste mais fácil!** 🎉

