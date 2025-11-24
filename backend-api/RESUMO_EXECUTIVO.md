# RESUMO EXECUTIVO - API RESTful de Tarefas

## ✅ CHECKLIST DE ENTREGA

### 1. Link do Projeto GitHub
- [ ] Link funcional: https://github.com/Srliper/api-java_bakend.git
- [ ] Repositório público e acessível
- [ ] Código commitado e enviado (push realizado)

### 2. Testes no Postman - PRINTS OBRIGATÓRIOS

#### Teste 1: Criação (POST)
- [ ] Print mostra método POST
- [ ] Print mostra URL: `http://localhost:8080/api/tarefas`
- [ ] Print mostra Body JSON com seu nome e RU
- [ ] Print mostra Status: `201 Created`
- [ ] Print mostra Response com tarefa criada contendo seu nome e RU

#### Teste 2: Listagem (GET)
- [ ] Print mostra método GET
- [ ] Print mostra URL: `http://localhost:8080/api/tarefas`
- [ ] Print mostra Status: `200 OK`
- [ ] Print mostra Response com array contendo tarefa com seu nome e RU

#### Teste 3: Atualização (PUT)
- [ ] Print mostra método PUT
- [ ] Print mostra URL com ID: `http://localhost:8080/api/tarefas/{id}`
- [ ] Print mostra Body JSON atualizado com seu nome e RU
- [ ] Print mostra Status: `200 OK`
- [ ] Print mostra Response com tarefa atualizada contendo seu nome e RU

#### Teste 4: Remoção (DELETE)
- [ ] Print mostra método DELETE
- [ ] Print mostra URL com ID: `http://localhost:8080/api/tarefas/{id}`
- [ ] Print mostra Status: `204 No Content`
- [ ] Print mostra que a tarefa com seu nome e RU foi removida

### 3. Documentação
- [ ] README.md completo
- [ ] POSTMAN_TESTES.md com exemplos
- [ ] CADERNO_ATIVIDADES_E_RESPOSTAS.md preenchido
- [ ] INSTRUCOES_PARA_PRINTS.md consultado

### 4. Funcionalidades Implementadas
- [x] Criar tarefa (POST)
- [x] Listar todas as tarefas (GET)
- [x] Buscar tarefa por ID (GET /{id})
- [x] Atualizar tarefa (PUT /{id})
- [x] Remover tarefa (DELETE /{id})

### 5. Requisitos Técnicos
- [x] Java com Spring Boot
- [x] Spring Data JPA
- [x] MySQL como banco de dados
- [x] Padrões REST implementados
- [x] Validações de dados
- [x] Tratamento de erros

---

## 📋 INFORMAÇÕES PARA PREENCHER NO CADERNO

**Aluno:** Luis Fernando Bedim  
**RU:** 4555952  
**Data de Entrega:** [PREENCHER]  
**Assinatura:** [PREENCHER]

---

## 🎯 PONTOS CRÍTICOS PARA NOTA

### Critério 1: Link do Projeto (25 pontos)
- ✅ Link funcional: https://github.com/Srliper/api-java_bakend.git
- ⚠️ Se link quebrado ou não fornecido: **NOTA 0**

### Critério 2: Teste 1 - Criação (25 pontos)
- ✅ Print com criação mostrando nome e RU
- ⚠️ Sem print ou sem nome/RU: **NOTA 0**

### Critério 3: Teste 2 - Listagem (25 pontos)
- ✅ Print com listagem mostrando tarefa com nome e RU
- ⚠️ Sem print: **NOTA 0**

### Critério 4: Teste 3 - Atualização (25 pontos)
- ✅ Print com atualização mostrando nome e RU
- ⚠️ Sem print ou sem evidência de atualização: **NOTA 0**

### Critério 5: Teste 4 - Remoção (25 pontos)
- ✅ Print com remoção (status 204)
- ⚠️ Sem print ou sem evidência de remoção: **NOTA 0**

---

## 📝 TEMPLATE DE JSON PARA TESTES

### Criar Tarefa (POST)
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Atualizar Tarefa (PUT)
```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

**✅ DADOS DO ALUNO:** Luis Fernando Bedim - RU: 4555952

---

## 🚀 COMANDOS GIT PARA ENVIAR AO GITHUB

```bash
cd backend-api
git add .
git commit -m "Implementa API RESTful de Tarefas - Trabalho Acadêmico"
git remote set-url origin https://github.com/Srliper/api-java_bakend.git
git push -u origin main
```

---

## ✅ VALIDAÇÃO FINAL ANTES DE ENTREGAR

Antes de entregar o caderno, verifique:

1. [ ] Link do GitHub está funcionando
2. [ ] Todos os 4 prints estão incluídos
3. [ ] Seu nome e RU aparecem nos prints 1, 2 e 3
4. [ ] Prints estão nítidos e legíveis
5. [ ] Caderno está preenchido completamente
6. [ ] Documentação está completa
7. [ ] Código está commitado no GitHub

---

**Boa sorte com a entrega! 🎓**

