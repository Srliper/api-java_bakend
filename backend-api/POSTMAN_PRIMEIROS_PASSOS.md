# 🚀 POSTMAN: PRIMEIROS PASSOS

## 🎯 ESCOLHA CORRETA: BLANK WORKSPACE

Quando abrir o Postman pela primeira vez, escolha:

✅ **Blank Workspace** (Espaço de Trabalho em Branco)

**NÃO escolha:**
❌ From Git Repository (não precisa)

---

## 📝 POR QUE BLANK WORKSPACE?

Você vai criar as requisições **manualmente** para testar sua API que está rodando localmente em `http://localhost:8080`.

**Não precisa importar do Git** porque:
- A API está rodando na sua máquina
- Você vai testar os endpoints diretamente
- É mais simples criar as requisições manualmente

---

## 🎯 PASSO A PASSO: CONFIGURAR POSTMAN

### 1. Abrir Postman
- Abra o aplicativo Postman (desktop ou web)

### 2. Criar Workspace
- Se perguntar, escolha: **"Blank Workspace"** ou **"My Workspace"**
- Ou clique em **"New"** → **"Workspace"** → **"Blank"**

### 3. Criar Nova Requisição
- Clique no botão **"New"** (canto superior esquerdo)
- Ou clique no **"+"** (aba de requisições)
- Selecione: **"HTTP Request"**

### 4. Configurar a Requisição
Agora você pode configurar:
- Método (GET, POST, PUT, DELETE)
- URL
- Headers
- Body

---

## 📋 EXEMPLO: CRIAR PRIMEIRA REQUISIÇÃO (POST)

### Passo a Passo:

1. **Clique em "New"** → **"HTTP Request"**

2. **Configure:**
   - Método: Selecione **POST** no dropdown
   - URL: Digite `http://localhost:8080/api/tarefas`

3. **Headers:**
   - Clique na aba **"Headers"**
   - Key: `Content-Type`
   - Value: `application/json`

4. **Body:**
   - Clique na aba **"Body"**
   - Selecione **"raw"**
   - No dropdown, escolha **"JSON"**
   - Cole o JSON:
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

5. **Salvar (opcional):**
   - Clique em **"Save"** ou `Ctrl+S`
   - Dê um nome: "Criar Tarefa"
   - Salve na coleção ou workspace

6. **Enviar:**
   - Clique no botão **"Send"**
   - Veja a resposta abaixo

---

## 💡 DICA: CRIAR COLEÇÃO

Para organizar melhor, crie uma coleção:

1. Clique em **"New"** → **"Collection"**
2. Nome: "API de Tarefas"
3. Agora você pode salvar todas as requisições nesta coleção

**Vantagens:**
- ✅ Organiza todas as requisições
- ✅ Pode exportar/importar depois
- ✅ Facilita encontrar as requisições

---

## 📝 REQUISIÇÕES PARA CRIAR

Crie estas 5 requisições na sua coleção:

### 1. Criar Tarefa (POST)
- Método: POST
- URL: `http://localhost:8080/api/tarefas`
- Body: JSON com dados da tarefa

### 2. Listar Tarefas (GET)
- Método: GET
- URL: `http://localhost:8080/api/tarefas`

### 3. Buscar Tarefa (GET)
- Método: GET
- URL: `http://localhost:8080/api/tarefas/{id}`

### 4. Atualizar Tarefa (PUT)
- Método: PUT
- URL: `http://localhost:8080/api/tarefas/{id}`
- Body: JSON com dados atualizados

### 5. Remover Tarefa (DELETE)
- Método: DELETE
- URL: `http://localhost:8080/api/tarefas/{id}`

---

## ✅ RESUMO

**Escolha:** ✅ **Blank Workspace**

**Por quê:**
- Você vai criar as requisições manualmente
- Não precisa importar do Git
- Mais simples e direto

**Próximos passos:**
1. Criar workspace em branco
2. Criar coleção "API de Tarefas"
3. Criar as 5 requisições
4. Testar cada uma
5. Tirar os prints

---

**Pronto para começar! 🚀**

