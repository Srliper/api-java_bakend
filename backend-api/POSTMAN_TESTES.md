# Guia de Testes - Postman

Este documento contém exemplos práticos para testar todos os endpoints da API de Tarefas usando o Postman.

## ⚙️ Configuração Inicial

1. Certifique-se de que a aplicação está rodando em `http://localhost:8080`
2. Certifique-se de que o MySQL está rodando e o banco `tarefasdb` foi criado
3. Abra o Postman

## 📝 Teste 1: Criar Tarefa (POST)

**Endpoint:** `POST http://localhost:8080/api/tarefas`

**Headers:**
```
Content-Type: application/json
```

**Body (raw JSON):**
```json
{
  "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
  "dataEntrega": "2025-12-10",
  "responsavel": "Luis Fernando Bedim - RU: 4555952"
}
```

**Resultado Esperado:**
- Status: `201 Created`
- Response body com a tarefa criada incluindo o ID gerado

**✅ DADOS DO ALUNO:** Luis Fernando Bedim - RU: 4555952

---

## 📋 Teste 2: Listar Todas as Tarefas (GET)

**Endpoint:** `GET http://localhost:8080/api/tarefas`

**Headers:** Não necessário

**Resultado Esperado:**
- Status: `200 OK`
- Response body com array de todas as tarefas cadastradas
- Deve incluir a tarefa criada no Teste 1 com seu nome e RU

**⚠️ IMPORTANTE:** Tire um print mostrando a lista com sua tarefa contendo seu nome e RU.

---

## 🔍 Teste 3: Buscar Tarefa por ID (GET)

**Endpoint:** `GET http://localhost:8080/api/tarefas/{id}`

**Exemplo:** `GET http://localhost:8080/api/tarefas/1`

**Resultado Esperado:**
- Status: `200 OK` (se encontrada)
- Response body com os dados da tarefa específica

**Teste de Erro:**
- Endpoint: `GET http://localhost:8080/api/tarefas/999`
- Status: `404 Not Found` (se não encontrada)

---

## ✏️ Teste 4: Atualizar Tarefa (PUT)

**Endpoint:** `PUT http://localhost:8080/api/tarefas/{id}`

**Exemplo:** `PUT http://localhost:8080/api/tarefas/1`

**Headers:**
```
Content-Type: application/json
```

**Body (raw JSON):**
```json
{
  "nome": "Trabalho Atualizado - API RESTful de Tarefas",
  "dataEntrega": "2025-12-15",
  "responsavel": "Luis Fernando Bedim - RU: 4555952"
}
```

**Resultado Esperado:**
- Status: `200 OK`
- Response body com a tarefa atualizada

**⚠️ IMPORTANTE:** 
- Atualize a tarefa que contém seu nome e RU
- Tire um print mostrando a tarefa atualizada

---

## 🗑️ Teste 5: Remover Tarefa (DELETE)

**Endpoint:** `DELETE http://localhost:8080/api/tarefas/{id}`

**Exemplo:** `DELETE http://localhost:8080/api/tarefas/1`

**Resultado Esperado:**
- Status: `204 No Content` (se removida com sucesso)
- Response body vazio

**Teste de Erro:**
- Endpoint: `DELETE http://localhost:8080/api/tarefas/999`
- Status: `404 Not Found` (se não encontrada)

**⚠️ IMPORTANTE:** 
- Remova a tarefa que contém seu nome e RU
- Tire um print mostrando o status 204 No Content

---

## 📸 Prints Necessários para Entrega

Conforme os critérios de avaliação, você precisa de prints mostrando:

1. **Teste 1 (Criação):** Print mostrando a criação com seu nome e RU
2. **Teste 2 (Listagem):** Print mostrando a lista com sua tarefa contendo nome e RU
3. **Teste 4 (Atualização):** Print mostrando a atualização da tarefa com seu nome e RU
4. **Teste 5 (Remoção):** Print mostrando a remoção da tarefa com seu nome e RU

## 🎯 Sequência Recomendada de Testes

1. Execute o **Teste 1** para criar uma tarefa com seu nome e RU
2. Execute o **Teste 2** para listar e confirmar que aparece
3. Execute o **Teste 3** para buscar por ID (opcional)
4. Execute o **Teste 4** para atualizar a tarefa
5. Execute o **Teste 2** novamente para ver a atualização na lista
6. Execute o **Teste 5** para remover a tarefa
7. Execute o **Teste 2** novamente para confirmar que foi removida

---

## ⚠️ Validações Implementadas

A API possui validações que retornam erro se:

- O campo `nome` estiver vazio ou com menos de 3 caracteres
- O campo `dataEntrega` não for informado
- O campo `responsavel` estiver vazio ou com menos de 3 caracteres

**Exemplo de Erro de Validação:**
```json
{
  "timestamp": "2025-11-21T15:30:00",
  "status": 400,
  "error": "Bad Request",
  "message": "Validation failed",
  "errors": [
    {
      "field": "nome",
      "message": "O nome da tarefa é obrigatório"
    }
  ]
}
```

---

## 🔗 Links Úteis

- **Repositório GitHub:** https://github.com/Srliper/api-java_bakend.git
- **Documentação Completa:** Ver README.md

