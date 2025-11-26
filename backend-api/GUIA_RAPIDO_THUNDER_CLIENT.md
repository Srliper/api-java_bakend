# ⚡ GUIA RÁPIDO: TESTAR E TIRAR PRINTS COM THUNDER CLIENT

## 🚀 PASSO 1: VERIFICAR SE SPRING BOOT ESTÁ RODANDO

**Antes de testar, certifique-se de que Spring Boot está rodando!**

1. Abra terminal na pasta `backend-api`
2. Execute:
```bash
mvnw.cmd spring-boot:run
```
3. Aguarde aparecer: **"Started BackendApiApplication"**
4. **NÃO feche este terminal!** Deixe rodando.

---

## ⚡ PASSO 2: ABRIR THUNDER CLIENT

1. No VS Code, procure o **ícone de raio** ⚡ na barra lateral esquerda
2. **Clique no ícone** ⚡
3. Thunder Client abrirá

---

## 🧪 TESTE 1: CRIAR TAREFA (POST)

### Configurar:
1. Clique em **"New Request"**
2. **Método:** POST
3. **URL:** `http://localhost:8080/api/tarefas`
4. **Headers:** 
   - Key: `Content-Type`
   - Value: `application/json`
5. **Body (JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Enviar:
- Clique em **"Send"**

### Resultado esperado:
- Status: **201 Created** (verde)
- Response mostra tarefa criada com "Luis 4555952"

### Tirar print:
1. Ajuste zoom: `Ctrl +` ou `Ctrl -`
2. `Windows + Shift + S`
3. Capture a tela do VS Code mostrando Request e Response
4. Salve como: `teste1.png`

---

## 🧪 TESTE 2: LISTAR TAREFAS (GET)

### Configurar:
1. **New Request**
2. **Método:** GET
3. **URL:** `http://localhost:8080/api/tarefas`
4. Headers e Body: **NÃO precisa**

### Enviar:
- **Send**

### Resultado esperado:
- Status: **200 OK**
- Response mostra array com tarefa contendo "Luis 4555952"

### Tirar print:
- `Windows + Shift + S`
- Capture tela
- Salve: `teste2.png`

---

## 🧪 TESTE 3: BUSCAR POR ID (GET)

### Configurar:
1. **New Request**
2. **Método:** GET
3. **URL:** `http://localhost:8080/api/tarefas/1` (use o ID do Teste 1)

### Enviar:
- **Send**

### Resultado esperado:
- Status: **200 OK**
- Response mostra tarefa com "Luis 4555952"

### Tirar print:
- `Windows + Shift + S`
- Salve: `teste3.png`

---

## 🧪 TESTE 4: ATUALIZAR (PUT)

### Configurar:
1. **New Request**
2. **Método:** PUT
3. **URL:** `http://localhost:8080/api/tarefas/1` (use o ID)
4. **Headers:** `Content-Type: application/json`
5. **Body (JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Enviar:
- **Send**

### Resultado esperado:
- Status: **200 OK**
- Response mostra tarefa atualizada com "Luis 4555952"

### Tirar print:
- `Windows + Shift + S`
- Salve: `teste4.png`

---

## 🧪 TESTE 5: REMOVER (DELETE)

### Configurar:
1. **New Request**
2. **Método:** DELETE
3. **URL:** `http://localhost:8080/api/tarefas/1` (use o ID)

### Enviar:
- **Send**

### Resultado esperado:
- Status: **204 No Content** (ou 200 OK)
- Response vazio (normal)

### Tirar print:
- `Windows + Shift + S`
- Salve: `teste5.png`

---

## 📸 COMO TIRAR PRINTS PERFEITOS

### Método 1: Windows + Shift + S (Recomendado)
1. Ajuste zoom do VS Code (`Ctrl +` ou `Ctrl -`)
2. Pressione `Windows + Shift + S`
3. Selecione área do VS Code com Thunder Client
4. Imagem copiada! Cole no Paint ou salve

### Método 2: Snipping Tool
1. Procure "Snipping Tool" no menu Iniciar
2. Clique em "New"
3. Selecione área do VS Code
4. Salve

### O que deve aparecer no print:
- ✅ Método HTTP (POST, GET, PUT, DELETE)
- ✅ URL completa
- ✅ Headers (se aplicável)
- ✅ Body JSON (se aplicável)
- ✅ Status code (201, 200, 204)
- ✅ Response body
- ✅ **"Luis 4555952"** claramente visível

---

## 📋 INSERIR PRINTS NO CADERNO

### Opção 1: No VS Code (Markdown)

1. Abra `CADERNO_ATIVIDADES_E_RESPOSTAS.md`
2. Encontre a seção do teste (ex: "TESTE 1")
3. Procure: `[INSERIR AQUI O PRINT...]`
4. Substitua por:
```markdown
![Teste 1 - Criar Tarefa](teste1.png)
```
5. Coloque a imagem na mesma pasta ou use caminho relativo

### Opção 2: No Word/DOCX

1. Abra o caderno em Word
2. Encontre a seção do teste
3. Clique em **Inserir** → **Imagens** → **Este Dispositivo**
4. Selecione o print salvo
5. Ajuste tamanho se necessário

---

## ✅ CHECKLIST FINAL

Antes de entregar, verifique:

- [ ] Spring Boot rodou sem erros
- [ ] Teste 1 (POST) funcionou - Status 201
- [ ] Teste 2 (GET) funcionou - Status 200
- [ ] Teste 3 (GET ID) funcionou - Status 200
- [ ] Teste 4 (PUT) funcionou - Status 200
- [ ] Teste 5 (DELETE) funcionou - Status 204
- [ ] Todos os prints mostram "Luis 4555952"
- [ ] Prints inseridos no caderno
- [ ] Caderno salvo em PDF ou DOCX

---

## 🎯 RESUMO ULTRA RÁPIDO

1. ✅ Rodar Spring Boot (`mvnw.cmd spring-boot:run`)
2. ✅ Abrir Thunder Client (ícone ⚡)
3. ✅ Fazer 5 testes (POST, GET, GET ID, PUT, DELETE)
4. ✅ Tirar prints (`Windows + Shift + S`)
5. ✅ Inserir prints no caderno
6. ✅ Salvar caderno em PDF/DOCX

**Pronto! 🎉**

