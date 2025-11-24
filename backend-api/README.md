# API RESTful de Gerenciamento de Tarefas

## 📋 Descrição do Projeto

API RESTful desenvolvida em **Java com Spring Boot** para gerenciamento completo de tarefas. A aplicação permite realizar operações CRUD (Create, Read, Update, Delete) em tarefas, contendo informações como nome da tarefa, data de entrega e responsável.

## 🛠️ Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.4.1**
- **Spring Data JPA** - Para manipulação de dados
- **MySQL** - Banco de dados relacional
- **Maven** - Gerenciamento de dependências

## 📦 Estrutura do Projeto

```
backend-api/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/backendapi/
│   │   │       ├── BackendApiApplication.java
│   │   │       ├── controller/
│   │   │       │   └── TarefaController.java
│   │   │       ├── model/
│   │   │       │   └── Tarefa.java
│   │   │       └── repository/
│   │   │           └── TarefaRepository.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
└── pom.xml
```

## 🗄️ Modelo de Dados

### Entidade Tarefa

A entidade `Tarefa` possui os seguintes atributos:

- **id** (Long) - Identificador único gerado automaticamente
- **nome** (String) - Nome da tarefa
- **dataEntrega** (LocalDate) - Data de entrega da tarefa
- **responsavel** (String) - Nome do responsável pela tarefa

## 🚀 Como Executar

### Pré-requisitos

1. **Java 17** ou superior instalado
2. **MySQL** instalado e rodando
3. **Maven** (ou usar o Maven Wrapper incluído)

### Configuração do Banco de Dados

1. Crie o banco de dados MySQL:
```sql
CREATE DATABASE tarefasdb;
```

2. Configure as credenciais no arquivo `application.properties`:
```properties
spring.datasource.username=root
spring.datasource.password=sua_senha
```

### Executando a Aplicação

1. Clone o repositório:
```bash
git clone https://github.com/Srliper/api-java_bakend.git
cd api-java_bakend/backend-api
```

2. Execute a aplicação:
```bash
# Windows
mvnw.cmd spring-boot:run

# Linux/Mac
./mvnw spring-boot:run
```

A aplicação estará disponível em: `http://localhost:8080`

## 📡 Endpoints da API

### Base URL
```
http://localhost:8080/api/tarefas
```

### 1. Criar Tarefa
**POST** `/api/tarefas`

**Request Body:**
```json
{
  "nome": "Implementar API REST",
  "dataEntrega": "2025-12-15",
  "responsavel": "João Silva - RU: 1234567"
}
```

**Response (200 OK):**
```json
{
  "id": 1,
  "nome": "Implementar API REST",
  "dataEntrega": "2025-12-15",
  "responsavel": "João Silva - RU: 1234567"
}
```

### 2. Listar Todas as Tarefas
**GET** `/api/tarefas`

**Response (200 OK):**
```json
[
  {
    "id": 1,
    "nome": "Implementar API REST",
    "dataEntrega": "2025-12-15",
    "responsavel": "João Silva - RU: 1234567"
  },
  {
    "id": 2,
    "nome": "Documentar API",
    "dataEntrega": "2025-12-20",
    "responsavel": "Maria Santos - RU: 7654321"
  }
]
```

### 3. Buscar Tarefa por ID
**GET** `/api/tarefas/{id}`

**Exemplo:** `GET /api/tarefas/1`

**Response (200 OK):**
```json
{
  "id": 1,
  "nome": "Implementar API REST",
  "dataEntrega": "2025-12-15",
  "responsavel": "João Silva - RU: 1234567"
}
```

**Response (404 Not Found):**
```json
{
  "status": 404,
  "error": "Not Found"
}
```

### 4. Atualizar Tarefa
**PUT** `/api/tarefas/{id}`

**Exemplo:** `PUT /api/tarefas/1`

**Request Body:**
```json
{
  "nome": "Implementar API REST - Atualizado",
  "dataEntrega": "2025-12-18",
  "responsavel": "João Silva - RU: 1234567"
}
```

**Response (200 OK):**
```json
{
  "id": 1,
  "nome": "Implementar API REST - Atualizado",
  "dataEntrega": "2025-12-18",
  "responsavel": "João Silva - RU: 1234567"
}
```

### 5. Remover Tarefa
**DELETE** `/api/tarefas/{id}`

**Exemplo:** `DELETE /api/tarefas/1`

**Response (204 No Content)** - Tarefa removida com sucesso

**Response (404 Not Found)** - Tarefa não encontrada

## 🧪 Testando com Postman

### Coleção de Exemplos

1. **Criar Tarefa:**
   - Método: `POST`
   - URL: `http://localhost:8080/api/tarefas`
   - Headers: `Content-Type: application/json`
   - Body (raw JSON):
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

2. **Listar Tarefas:**
   - Método: `GET`
   - URL: `http://localhost:8080/api/tarefas`

3. **Buscar Tarefa:**
   - Método: `GET`
   - URL: `http://localhost:8080/api/tarefas/1`

4. **Atualizar Tarefa:**
   - Método: `PUT`
   - URL: `http://localhost:8080/api/tarefas/1`
   - Body (raw JSON):
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

5. **Remover Tarefa:**
   - Método: `DELETE`
   - URL: `http://localhost:8080/api/tarefas/1`

## 📝 Padrões REST Implementados

- ✅ **GET** para consultas (listar e buscar)
- ✅ **POST** para criação de recursos
- ✅ **PUT** para atualização completa
- ✅ **DELETE** para remoção
- ✅ Códigos HTTP apropriados (200, 201, 204, 404)
- ✅ JSON como formato de dados

## 🔧 Configurações

### application.properties

```properties
# Nome da aplicação
spring.application.name=tarefa-api

# Configuração do banco de dados MySQL
spring.datasource.url=jdbc:mysql://localhost:3306/tarefasdb?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Configuração JPA/Hibernate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.show-sql=true

# Formatação de datas
spring.jackson.serialization.write-dates-as-timestamps=false
```

## 👨‍💻 Autor

Desenvolvido como trabalho acadêmico para a disciplina de Desenvolvimento Web Backend.

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais.

---

**Repositório GitHub:** https://github.com/Srliper/api-java_bakend.git

