# 📸 INSTRUÇÕES DETALHADAS PARA TIRAR OS PRINTS NO POSTMAN

Este documento fornece instruções passo a passo para tirar os prints corretos que devem ser inseridos no Caderno de Atividades.

---

## ⚠️ IMPORTANTE: ANTES DE COMEÇAR

1. **Dados do Aluno:**
   - Nome: Luis Fernando Bedim
   - RU: 4555952

2. **Certifique-se de que:**
   - A aplicação Spring Boot está rodando
   - O MySQL está rodando e o banco `tarefasdb` foi criado
   - Você está conectado ao Postman

---

## 📸 PRINT 1: TESTE DE CRIAÇÃO (POST)

### Passo a Passo:

1. **Configure a requisição:**
   - Método: `POST`
   - URL: `http://localhost:8080/api/tarefas`
   - Aba "Headers": Adicione `Content-Type: application/json`
   - Aba "Body": Selecione "raw" e "JSON"
   - Cole o JSON:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

2. **Clique em "Send"**

3. **Tire o print mostrando:**
   - ✅ Método POST visível
   - ✅ URL completa
   - ✅ Body JSON com seu nome e RU
   - ✅ Status: `201 Created`
   - ✅ Response body mostrando a tarefa criada com seu nome e RU

4. **O que deve aparecer no print:**
   - Painel esquerdo: Request (POST, URL, Body)
   - Painel direito: Response (Status 201, Body com JSON da tarefa criada)
   - **IMPORTANTE:** O campo "responsavel" na resposta DEVE mostrar seu nome e RU

---

## 📸 PRINT 2: TESTE DE LISTAGEM (GET)

### Passo a Passo:

1. **Configure a requisição:**
   - Método: `GET`
   - URL: `http://localhost:8080/api/tarefas`

2. **Clique em "Send"**

3. **Tire o print mostrando:**
   - ✅ Método GET visível
   - ✅ URL completa
   - ✅ Status: `200 OK`
   - ✅ Response body com array JSON
   - ✅ A tarefa na lista DEVE conter seu nome e RU no campo "responsavel"

4. **O que deve aparecer no print:**
   - Painel esquerdo: Request (GET, URL)
   - Painel direito: Response (Status 200, Body com array JSON)
   - **IMPORTANTE:** O array deve conter pelo menos uma tarefa com seu nome e RU visíveis

---

## 📸 PRINT 3: TESTE DE ATUALIZAÇÃO (PUT)

### Passo a Passo:

1. **Primeiro, anote o ID da tarefa criada** (do Print 1, geralmente será `1`)

2. **Configure a requisição:**
   - Método: `PUT`
   - URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)
   - Aba "Headers": Adicione `Content-Type: application/json`
   - Aba "Body": Selecione "raw" e "JSON"
   - Cole o JSON:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

3. **Clique em "Send"**

4. **Tire o print mostrando:**
   - ✅ Método PUT visível
   - ✅ URL completa com o ID
   - ✅ Body JSON com dados atualizados contendo seu nome e RU
   - ✅ Status: `200 OK`
   - ✅ Response body mostrando a tarefa atualizada com seu nome e RU

5. **O que deve aparecer no print:**
   - Painel esquerdo: Request (PUT, URL com ID, Body)
   - Painel direito: Response (Status 200, Body com JSON da tarefa atualizada)
   - **IMPORTANTE:** O campo "responsavel" na resposta DEVE mostrar seu nome e RU

---

## 📸 PRINT 4: TESTE DE REMOÇÃO (DELETE)

### Passo a Passo:

1. **Use o mesmo ID da tarefa** (do Print 1 e 3)

2. **Configure a requisição:**
   - Método: `DELETE`
   - URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)

3. **Clique em "Send"**

4. **Tire o print mostrando:**
   - ✅ Método DELETE visível
   - ✅ URL completa com o ID da tarefa que contém seu nome e RU
   - ✅ Status: `204 No Content`
   - ✅ Response body vazio (ou mensagem "No Content")

5. **O que deve aparecer no print:**
   - Painel esquerdo: Request (DELETE, URL com ID)
   - Painel direito: Response (Status 204 No Content)
   - **IMPORTANTE:** O status 204 deve estar claramente visível

6. **Print Adicional (Opcional mas Recomendado):**
   - Após a remoção, execute GET `/api/tarefas` novamente
   - Deve retornar array vazio `[]`
   - Tire um print adicional mostrando isso

---

## ✅ CHECKLIST ANTES DE ENTREGAR

Antes de inserir os prints no caderno, verifique:

- [ ] Print 1: Mostra criação com seu nome e RU?
- [ ] Print 2: Mostra lista com tarefa contendo seu nome e RU?
- [ ] Print 3: Mostra atualização com seu nome e RU?
- [ ] Print 4: Mostra remoção (status 204)?
- [ ] Todos os prints estão nítidos e legíveis?
- [ ] Seu nome e RU estão visíveis nos prints 1, 2 e 3?
- [ ] Os métodos HTTP estão claramente visíveis?
- [ ] Os status codes estão visíveis?

---

## 💡 DICAS PARA PRINTS MELHORES

1. **Use a ferramenta de screenshot do Windows:**
   - `Windows + Shift + S` para captura de tela
   - Ou use a ferramenta "Snipping Tool"

2. **Ajuste o zoom do Postman:**
   - Use `Ctrl + Scroll` para ajustar o zoom
   - Garanta que todo o conteúdo importante esteja visível

3. **Organize as abas:**
   - Feche abas desnecessárias do Postman
   - Foque apenas na requisição que está testando

4. **Capture a tela completa:**
   - Inclua tanto o Request quanto o Response
   - Mostre os Headers se relevante
   - Mostre o Status Code claramente

---

## 🎯 EXEMPLO DE COMO DEVE FICAR

Cada print deve mostrar claramente:

```
┌─────────────────────────────────────┐
│ POST  http://localhost:8080/api/... │
│ Headers: Content-Type: application/ │
│ Body: { "nome": "...", "responsavel": "Luis Fernando Bedim - RU: 4555952" } │
├─────────────────────────────────────┤
│ Status: 201 Created                 │
│ Body: { "id": 1, "nome": "...",     │
│         "responsavel": "Luis Fernando Bedim - RU: 4555952" } │
└─────────────────────────────────────┘
```

---

**Lembre-se:** Sem os prints com evidências claras do seu nome e RU, a nota será ZERO conforme os critérios de avaliação!

