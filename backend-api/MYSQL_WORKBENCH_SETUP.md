# 🗄️ CONFIGURAÇÃO DO MYSQL WORKBENCH

## 🎯 INTEGRAÇÃO COM MYSQL WORKBENCH

Este guia mostra como configurar o MySQL Workbench para trabalhar com a API.

---

## 📋 PRÉ-REQUISITOS

- ✅ MySQL instalado
- ✅ MySQL Workbench instalado
- ✅ API Spring Boot configurada

---

## 🚀 PASSO 1: ABRIR MYSQL WORKBENCH

1. Abra o **MySQL Workbench**
2. Conecte-se ao servidor MySQL local:
   - Clique na conexão local (geralmente "Local instance MySQL" ou similar)
   - Ou crie nova conexão se necessário

---

## 🚀 PASSO 2: CRIAR O BANCO DE DADOS

1. **Abra uma nova query** (File → New Query Tab ou `Ctrl+T`)

2. **Execute este comando SQL:**
```sql
CREATE DATABASE tarefasdb;
```

3. **Verifique se foi criado:**
```sql
SHOW DATABASES;
```
Deve aparecer `tarefasdb` na lista.

4. **Selecione o banco:**
```sql
USE tarefasdb;
```

---

## 🚀 PASSO 3: VERIFICAR CONFIGURAÇÃO DA API

O arquivo `application.properties` já está configurado:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/tarefasdb
spring.datasource.username=root
spring.datasource.password=root
```

**Se sua senha do MySQL não for `root`:**
- Abra: `backend-api/src/main/resources/application.properties`
- Altere: `spring.datasource.password=sua_senha_aqui`

---

## 🚀 PASSO 4: EXECUTAR A APLICAÇÃO

1. **Inicie a aplicação Spring Boot:**
```bash
cd backend-api
mvnw.cmd spring-boot:run
```

2. **Aguarde a mensagem:**
```
Started BackendApiApplication in X.XXX seconds
```

3. **O Hibernate vai criar a tabela automaticamente!**

---

## 🚀 PASSO 5: VERIFICAR NO MYSQL WORKBENCH

1. **No MySQL Workbench, atualize o schema:**
   - Clique com botão direito em `tarefasdb`
   - Selecione "Refresh All"

2. **Veja a tabela criada:**
   - Expanda `tarefasdb` → `Tables`
   - Deve aparecer a tabela `tarefas`

3. **Veja a estrutura da tabela:**
   - Clique com botão direito em `tarefas` → "Table Inspector"
   - Ou execute:
   ```sql
   DESCRIBE tarefas;
   ```

**Estrutura esperada:**
```
+---------------+--------------+------+-----+---------+----------------+
| Field         | Type         | Null | Key | Default | Extra          |
+---------------+--------------+------+-----+---------+----------------+
| id            | bigint       | NO   | PRI | NULL    | auto_increment |
| nome          | varchar(200) | NO   |     | NULL    |                |
| data_entrega  | date         | NO   |     | NULL    |                |
| responsavel   | varchar(100) | NO   |     | NULL    |                |
+---------------+--------------+------+-----+---------+----------------+
```

---

## 🧪 TESTAR A INTEGRAÇÃO

### 1. Criar Tarefa via API (Postman)
- POST `http://localhost:8080/api/tarefas`
- Body com dados da tarefa

### 2. Verificar no MySQL Workbench
```sql
USE tarefasdb;
SELECT * FROM tarefas;
```

**Deve mostrar a tarefa criada!** ✅

---

## 📊 COMANDOS ÚTEIS NO MYSQL WORKBENCH

### Ver todas as tarefas:
```sql
SELECT * FROM tarefas;
```

### Ver tarefa específica:
```sql
SELECT * FROM tarefas WHERE id = 1;
```

### Contar tarefas:
```sql
SELECT COUNT(*) FROM tarefas;
```

### Limpar todas as tarefas (cuidado!):
```sql
DELETE FROM tarefas;
```

### Ver estrutura da tabela:
```sql
DESCRIBE tarefas;
```

---

## ⚠️ PROBLEMAS COMUNS

### Erro: "Access denied for user 'root'@'localhost'"
**Solução:**
- Verifique a senha no `application.properties`
- Teste a conexão no MySQL Workbench primeiro

### Erro: "Unknown database 'tarefasdb'"
**Solução:**
- Execute: `CREATE DATABASE tarefasdb;` no MySQL Workbench

### Tabela não aparece
**Solução:**
- Certifique-se de que a aplicação Spring Boot está rodando
- O Hibernate cria a tabela na primeira execução
- Atualize o schema no Workbench (Refresh)

---

## ✅ CHECKLIST DE INTEGRAÇÃO

- [ ] MySQL Workbench instalado e funcionando
- [ ] Banco `tarefasdb` criado
- [ ] Senha do MySQL configurada no `application.properties`
- [ ] Aplicação Spring Boot iniciada
- [ ] Tabela `tarefas` criada automaticamente
- [ ] Pode ver dados no MySQL Workbench
- [ ] API funciona corretamente

---

## 🎯 RESUMO

**MySQL Workbench é usado para:**
- ✅ Criar o banco de dados
- ✅ Ver os dados inseridos pela API
- ✅ Verificar estrutura das tabelas
- ✅ Executar queries SQL manualmente

**A API Spring Boot:**
- ✅ Conecta automaticamente ao MySQL
- ✅ Cria a tabela automaticamente (Hibernate)
- ✅ Insere/atualiza/remove dados via endpoints REST

**Tudo integrado e funcionando!** ✅

---

**Pronto para usar MySQL Workbench! 🗄️**

