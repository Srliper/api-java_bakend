# 🧪 GUIA COMPLETO: COMO TESTAR A API

Este guia vai te ajudar a testar toda a API passo a passo para garantir que está tudo funcionando antes de tirar os prints para o trabalho.

---

## 📋 PRÉ-REQUISITOS

Antes de começar, verifique se você tem:

- [ ] Java 17 ou superior instalado
- [ ] MySQL instalado e rodando
- [ ] Postman instalado (ou pode usar o navegador para GET)

### Verificar Java
```bash
java -version
```
Deve mostrar versão 17 ou superior.

### Verificar MySQL
Abra o MySQL Workbench ou linha de comando e verifique se está rodando.

---

## 🚀 PASSO 1: CONFIGURAR O BANCO DE DADOS

1. **Abra o MySQL** (Workbench ou linha de comando)

2. **Crie o banco de dados:**
```sql
CREATE DATABASE tarefasdb;
```

3. **Verifique se foi criado:**
```sql
SHOW DATABASES;
```
Deve aparecer `tarefasdb` na lista.

4. **Configure a senha no arquivo `application.properties`** se necessário:
   - Abra: `backend-api/src/main/resources/application.properties`
   - Se sua senha do MySQL não for `root`, altere:
   ```properties
   spring.datasource.password=sua_senha_aqui
   ```

---

## 🚀 PASSO 2: INICIAR A APLICAÇÃO

1. **Abra o terminal/PowerShell** na pasta do projeto:
```bash
cd C:\Users\acer\Desktop\bakend-API\backend-api
```

2. **Execute a aplicação:**
```bash
# Windows
mvnw.cmd spring-boot:run

# Ou se tiver Maven instalado
mvn spring-boot:run
```

3. **Aguarde a mensagem de sucesso:**
```
Started BackendApiApplication in X.XXX seconds
```

4. **Verifique se não há erros:**
   - Se aparecer erro de conexão com MySQL, verifique:
     - MySQL está rodando?
     - Senha está correta no `application.properties`?
     - Banco `tarefasdb` foi criado?

---

## 🧪 PASSO 3: TESTAR NO POSTMAN

### Teste 1: Criar Tarefa (POST) ✅

1. **Abra o Postman**

2. **Configure a requisição:**
   - Método: `POST`
   - URL: `http://localhost:8080/api/tarefas`
   - Aba "Headers": 
     - Key: `Content-Type`
     - Value: `application/json`
   - Aba "Body":
     - Selecione "raw"
     - Selecione "JSON" no dropdown
     - Cole este JSON:
     ```json
     {
       "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
       "dataEntrega": "2025-12-10",
       "responsavel": "Luis Fernando Bedim - RU: 4555952"
     }
     ```

3. **Clique em "Send"**

4. **Resultado esperado:**
   - Status: `201 Created` ✅
   - Response body deve mostrar:
     ```json
     {
       "id": 1,
       "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
       "dataEntrega": "2025-12-10",
       "responsavel": "Luis Fernando Bedim - RU: 4555952"
     }
     ```

5. **Anote o ID retornado** (geralmente será `1`)

**✅ Se funcionou:** A tarefa foi criada! Pode tirar o print agora.

---

### Teste 2: Listar Todas as Tarefas (GET) ✅

1. **No Postman, crie nova requisição:**
   - Método: `GET`
   - URL: `http://localhost:8080/api/tarefas`
   - Não precisa de Headers ou Body

2. **Clique em "Send"**

3. **Resultado esperado:**
   - Status: `200 OK` ✅
   - Response body deve mostrar um array:
     ```json
     [
       {
         "id": 1,
         "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
         "dataEntrega": "2025-12-10",
         "responsavel": "Luis Fernando Bedim - RU: 4555952"
       }
     ]
     ```

**✅ Se funcionou:** A lista está funcionando! Pode tirar o print agora.

---

### Teste 3: Buscar Tarefa por ID (GET) ✅

1. **No Postman:**
   - Método: `GET`
   - URL: `http://localhost:8080/api/tarefas/1` (use o ID da tarefa criada)

2. **Clique em "Send"**

3. **Resultado esperado:**
   - Status: `200 OK` ✅
   - Response body deve mostrar apenas a tarefa com ID 1

**Teste de erro (opcional):**
- URL: `http://localhost:8080/api/tarefas/999`
- Deve retornar: `404 Not Found` ✅

---

### Teste 4: Atualizar Tarefa (PUT) ✅

1. **No Postman:**
   - Método: `PUT`
   - URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)
   - Aba "Headers": 
     - Key: `Content-Type`
     - Value: `application/json`
   - Aba "Body":
     - Selecione "raw" e "JSON"
     - Cole este JSON:
     ```json
     {
       "nome": "Trabalho Atualizado - API RESTful de Tarefas",
       "dataEntrega": "2025-12-15",
       "responsavel": "Luis Fernando Bedim - RU: 4555952"
     }
     ```

2. **Clique em "Send"**

3. **Resultado esperado:**
   - Status: `200 OK` ✅
   - Response body deve mostrar a tarefa atualizada:
     ```json
     {
       "id": 1,
       "nome": "Trabalho Atualizado - API RESTful de Tarefas",
       "dataEntrega": "2025-12-15",
       "responsavel": "Luis Fernando Bedim - RU: 4555952"
     }
     ```

4. **Verifique a atualização:**
   - Execute GET `/api/tarefas` novamente
   - Deve mostrar a tarefa com o nome atualizado

**✅ Se funcionou:** A atualização está funcionando! Pode tirar o print agora.

---

### Teste 5: Remover Tarefa (DELETE) ✅

1. **No Postman:**
   - Método: `DELETE`
   - URL: `http://localhost:8080/api/tarefas/1` (use o ID correto)

2. **Clique em "Send"**

3. **Resultado esperado:**
   - Status: `204 No Content` ✅
   - Response body vazio (ou mensagem "No Content")

4. **Verifique a remoção:**
   - Execute GET `/api/tarefas` novamente
   - Deve retornar array vazio: `[]`

**✅ Se funcionou:** A remoção está funcionando! Pode tirar o print agora.

---

## 🎯 CHECKLIST DE TESTES

Marque conforme for testando:

- [ ] ✅ Aplicação inicia sem erros
- [ ] ✅ Banco de dados conecta corretamente
- [ ] ✅ POST cria tarefa (Status 201)
- [ ] ✅ GET lista todas as tarefas (Status 200)
- [ ] ✅ GET busca tarefa por ID (Status 200)
- [ ] ✅ PUT atualiza tarefa (Status 200)
- [ ] ✅ DELETE remove tarefa (Status 204)
- [ ] ✅ Validações funcionam (campos obrigatórios)
- [ ] ✅ Erro 404 aparece quando ID não existe

---

## ⚠️ PROBLEMAS COMUNS E SOLUÇÕES

### Erro: "Connection refused" ou "Communications link failure"
**Causa:** MySQL não está rodando ou senha incorreta

**Solução:**
1. Verifique se MySQL está rodando
2. Verifique a senha no `application.properties`
3. Verifique se o banco `tarefasdb` foi criado

### Erro: "Port 8080 already in use"
**Causa:** Outra aplicação está usando a porta 8080

**Solução:**
1. Feche outras aplicações na porta 8080
2. Ou altere a porta no `application.properties`:
   ```properties
   server.port=8081
   ```

### Erro: "Validation failed" (Status 400)
**Causa:** Campos obrigatórios não foram preenchidos

**Solução:**
- Verifique se todos os campos estão no JSON:
  - `nome` (obrigatório, mínimo 3 caracteres)
  - `dataEntrega` (obrigatório)
  - `responsavel` (obrigatório, mínimo 3 caracteres)

### Erro: "404 Not Found" ao acessar endpoints
**Causa:** Aplicação não está rodando ou URL incorreta

**Solução:**
1. Verifique se a aplicação está rodando
2. Verifique a URL: `http://localhost:8080/api/tarefas`
3. Verifique se não há erro no console

---

## 📸 QUANDO TIRAR OS PRINTS

Tire os prints **APENAS** quando:

1. ✅ Todos os testes passaram
2. ✅ Status codes estão corretos (201, 200, 204)
3. ✅ Seu nome e RU aparecem nas respostas
4. ✅ Tudo está funcionando perfeitamente

**Prints necessários:**
1. Print do Teste 1 (POST) - Criação
2. Print do Teste 2 (GET) - Listagem
3. Print do Teste 4 (PUT) - Atualização
4. Print do Teste 5 (DELETE) - Remoção

---

## 🎉 SE TUDO FUNCIONOU!

Parabéns! Sua API está funcionando perfeitamente. Agora você pode:

1. ✅ Tirar os prints no Postman
2. ✅ Inserir os prints no caderno
3. ✅ Converter para PDF/DOCX
4. ✅ Entregar o trabalho

---

## 💡 DICA EXTRA

**Teste rápido no navegador:**
Você pode testar o GET diretamente no navegador:
- Abra: `http://localhost:8080/api/tarefas`
- Deve mostrar o JSON das tarefas

Isso ajuda a verificar se a API está respondendo!

---

**Boa sorte com os testes! 🚀**

