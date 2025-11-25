# 🚀 GUIA COMPLETO: DO ZERO AOS PRINTS

## 🎯 FLUXO COMPLETO: CONECTAR TUDO E TIRAR OS PRINTS

Este guia mostra **passo a passo** como conectar Spring Boot + MySQL + Postman e tirar os prints.

---

## 📋 PASSO 1: VERIFICAR SE TUDO ESTÁ INSTALADO

### Checklist:
- [ ] Java instalado (você tem Java 23 ✅)
- [ ] MySQL instalado e rodando
- [ ] MySQL Workbench instalado
- [ ] Postman instalado
- [ ] Projeto Spring Boot pronto (já está ✅)

---

## 🗄️ PASSO 2: CONFIGURAR MYSQL

### 2.1 Abrir MySQL Workbench

1. Abra o **MySQL Workbench**
2. Conecte ao servidor MySQL local

### 2.2 Criar o Banco de Dados

1. **Abra uma nova query** (`Ctrl+T`)

2. **Execute:**
```sql
CREATE DATABASE tarefasdb;
```

3. **Verifique:**
```sql
SHOW DATABASES;
```
Deve aparecer `tarefasdb` na lista.

### 2.3 Verificar Senha do MySQL

- Se sua senha do MySQL **não for `root`**, edite:
  - Arquivo: `backend-api/src/main/resources/application.properties`
  - Linha: `spring.datasource.password=root`
  - Altere para sua senha real

---

## 🚀 PASSO 3: INICIAR A APLICAÇÃO SPRING BOOT

### 3.1 Abrir Terminal

1. Abra o **PowerShell** ou **Prompt de Comando**
2. Navegue até a pasta do projeto:
```bash
cd C:\Users\acer\Desktop\bakend-API\backend-api
```

### 3.2 Executar a Aplicação

```bash
mvnw.cmd spring-boot:run
```

### 3.3 Aguardar Inicialização

Você deve ver:
```
Started BackendApiApplication in X.XXX seconds
```

**⚠️ Se aparecer erro:**
- Verifique se MySQL está rodando
- Verifique se o banco `tarefasdb` foi criado
- Verifique a senha no `application.properties`

### 3.4 Deixar Rodando

**⚠️ IMPORTANTE:** Deixe este terminal aberto e rodando!
- Não feche o terminal
- A aplicação precisa estar rodando para o Postman funcionar

---

## 📮 PASSO 4: CONFIGURAR POSTMAN

### 4.1 Abrir Postman

1. Abra o **Postman** (aplicativo desktop ou web)

2. Escolha: **Blank Workspace**

### 4.2 Criar Coleção (Opcional)

1. Clique em **"New"** → **"Collection"**
2. Nome: **"API de Tarefas"**
3. Clique em **"Create"**

---

## 🧪 PASSO 5: TESTAR OS ENDPOINTS E TIRAR PRINTS

### TESTE 1: CRIAR TAREFA (POST) 📸

#### 5.1 Criar Requisição

1. Clique no **"+"** (criar nova requisição)
2. Nome: **"Criar Tarefa"**

#### 5.2 Configurar

- **Método:** POST
- **URL:** `http://localhost:8080/api/tarefas`
- **Headers:**
  - Key: `Content-Type`
  - Value: `application/json`
- **Body (raw JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

#### 5.3 Enviar e Verificar

1. Clique em **"Send"**
2. Deve aparecer:
   - Status: **201 Created**
   - Response com a tarefa criada incluindo `"responsavel": "Luis 4555952"`

#### 5.4 Tirar Print 📸

1. **Ajuste a tela** para mostrar Request e Response
2. **Use `Windows + Shift + S`** para captura de tela
3. **Capture:**
   - Método POST
   - URL
   - Body JSON com "Luis 4555952"
   - Status 201 Created
   - Response com "Luis 4555952" visível

4. **Salve o print** com nome: "Teste1_POST_CriarTarefa.png"

#### 5.5 Anotar o ID

- Na resposta, veja o campo `"id"` (geralmente será `1`)
- Anote este ID para os próximos testes

---

### TESTE 2: LISTAR TAREFAS (GET) 📸

#### 5.6 Criar Requisição

1. Clique no **"+"** novamente
2. Nome: **"Listar Tarefas"**

#### 5.7 Configurar

- **Método:** GET
- **URL:** `http://localhost:8080/api/tarefas`
- **Headers:** Não precisa
- **Body:** Não precisa

#### 5.8 Enviar e Verificar

1. Clique em **"Send"**
2. Deve aparecer:
   - Status: **200 OK**
   - Response com array contendo sua tarefa
   - `"responsavel": "Luis 4555952"` deve estar visível

#### 5.9 Tirar Print 📸

1. **Capture a tela** mostrando:
   - Método GET
   - URL
   - Status 200 OK
   - Response com array
   - "Luis 4555952" visível na lista

2. **Salve:** "Teste2_GET_ListarTarefas.png"

---

### TESTE 3: ATUALIZAR TAREFA (PUT) 📸

#### 5.10 Criar Requisição

1. Clique no **"+"** novamente
2. Nome: **"Atualizar Tarefa"**

#### 5.11 Configurar

- **Método:** PUT
- **URL:** `http://localhost:8080/api/tarefas/1` (use o ID anotado)
- **Headers:**
  - Key: `Content-Type`
  - Value: `application/json`
- **Body (raw JSON):**
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

#### 5.12 Enviar e Verificar

1. Clique em **"Send"**
2. Deve aparecer:
   - Status: **200 OK**
   - Response com tarefa atualizada
   - `"responsavel": "Luis 4555952"` visível

#### 5.13 Tirar Print 📸

1. **Capture a tela** mostrando:
   - Método PUT
   - URL com ID
   - Body JSON com "Luis 4555952"
   - Status 200 OK
   - Response com "Luis 4555952" visível

2. **Salve:** "Teste3_PUT_AtualizarTarefa.png"

---

### TESTE 4: REMOVER TAREFA (DELETE) 📸

#### 5.14 Criar Requisição

1. Clique no **"+"** novamente
2. Nome: **"Remover Tarefa"`

#### 5.15 Configurar

- **Método:** DELETE
- **URL:** `http://localhost:8080/api/tarefas/1` (use o ID anotado)
- **Headers:** Não precisa
- **Body:** Não precisa

#### 5.16 Enviar e Verificar

1. Clique em **"Send"**
2. Deve aparecer:
   - Status: **204 No Content**
   - Response vazio (ou "No Content")

#### 5.17 Tirar Print 📸

1. **Capture a tela** mostrando:
   - Método DELETE
   - URL com ID
   - Status 204 No Content

2. **Salve:** "Teste4_DELETE_RemoverTarefa.png"

---

## 📝 PASSO 6: INSERIR PRINTS NO CADERNO

### 6.1 Abrir o Caderno

1. Abra o arquivo: `CADERNO_ATIVIDADES_E_RESPOSTAS.md`

### 6.2 Inserir os Prints

1. **Teste 1:** Procure a seção "TESTE 1: Criação de Tarefa (POST)"
   - Insira o print "Teste1_POST_CriarTarefa.png"
   - Ou cole a imagem diretamente

2. **Teste 2:** Procure a seção "TESTE 2: Listagem de Tarefas (GET)"
   - Insira o print "Teste2_GET_ListarTarefas.png"

3. **Teste 3:** Procure a seção "TESTE 3: Atualização de Tarefa (PUT)"
   - Insira o print "Teste3_PUT_AtualizarTarefa.png"

4. **Teste 4:** Procure a seção "TESTE 4: Remoção de Tarefa (DELETE)"
   - Insira o print "Teste4_DELETE_RemoverTarefa.png"

### 6.3 Preencher Dados Finais

- Data de entrega: _______________
- Assinatura: _______________

---

## 📄 PASSO 7: CONVERTER PARA PDF/DOCX

### Opção 1: Converter Markdown para PDF

1. Use um conversor online:
   - https://www.markdowntopdf.com/
   - Ou https://dillinger.io/ (exportar como PDF)

2. Ou use o Word:
   - Abra o arquivo `.md` no Word
   - Salve como PDF ou DOCX

### Opção 2: Copiar para Word

1. Abra o `CADERNO_ATIVIDADES_E_RESPOSTAS.md`
2. Copie todo o conteúdo
3. Cole no Microsoft Word
4. Insira os prints nas seções indicadas
5. Salve como PDF ou DOCX

---

## ✅ CHECKLIST FINAL

Antes de entregar, verifique:

- [ ] MySQL rodando
- [ ] Banco `tarefasdb` criado
- [ ] Aplicação Spring Boot rodando
- [ ] Teste 1 executado e print tirado
- [ ] Teste 2 executado e print tirado
- [ ] Teste 3 executado e print tirado
- [ ] Teste 4 executado e print tirado
- [ ] Prints inseridos no caderno
- [ ] Link do GitHub no caderno
- [ ] Dados do aluno preenchidos
- [ ] Caderno convertido para PDF/DOCX
- [ ] Arquivo pronto para entrega

---

## 🎯 RESUMO DO FLUXO

```
1. MySQL Workbench → Criar banco "tarefasdb"
   ↓
2. Terminal → Executar "mvnw.cmd spring-boot:run"
   ↓
3. Postman → Criar requisições (POST, GET, PUT, DELETE)
   ↓
4. Postman → Testar cada endpoint
   ↓
5. Postman → Tirar prints de cada teste
   ↓
6. Caderno → Inserir os prints
   ↓
7. Converter → PDF ou DOCX
   ↓
8. Entregar → Arquivo final
```

---

## 💡 DICAS IMPORTANTES

### Durante os Testes:
- ✅ Deixe a aplicação Spring Boot rodando
- ✅ Não feche o terminal enquanto testa
- ✅ Teste na ordem: POST → GET → PUT → DELETE
- ✅ Verifique se "Luis 4555952" aparece em todos os prints

### Nos Prints:
- ✅ Capture Request e Response juntos
- ✅ Certifique-se de que o texto está legível
- ✅ "Luis 4555952" deve estar claramente visível
- ✅ Status codes devem estar visíveis

---

## 🚀 PRONTO PARA COMEÇAR!

**Sequência:**
1. MySQL Workbench → Criar banco
2. Terminal → Iniciar aplicação
3. Postman → Testar endpoints
4. Tirar prints
5. Inserir no caderno
6. Converter e entregar

**Tudo conectado e funcionando!** ✅

---

**Boa sorte com os testes! 🎯**

