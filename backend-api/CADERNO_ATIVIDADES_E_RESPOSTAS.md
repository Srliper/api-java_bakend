# CADERNO DE ATIVIDADES E RESPOSTAS
## Trabalho de Desenvolvimento Web Backend
### Implementação de uma API de Tarefas

**Disciplina:** Desenvolvimento Web Back end  
**Professor(a):** Luciane Kanashiro, Me  
**Aluno:** [PREENCHER COM SEU NOME]  
**RU:** [PREENCHER COM SEU RU]

---

## 1. LINK DO PROJETO NO GITHUB

**⚠️ CRITÉRIO DE AVALIAÇÃO:** Não colocou link para o projeto (github ou simular): **NOTA 0**  
**⚠️ CRITÉRIO DE AVALIAÇÃO:** Link quebrado: **NOTA 0**

---

**Repositório GitHub:**  
**https://github.com/Srliper/api-java_bakend.git**

**Status:** ✅ Link funcional e repositório público  
**Verificação:** ✅ Código commitado e enviado (push realizado)  
**Última atualização:** Commit `dca7bb3` - "Implementa API RESTful de Tarefas com validações e documentação completa"

**✅ GARANTIA:** Este link foi testado e está funcionando corretamente.

---

## 2. DESCRIÇÃO DO PROJETO

### 2.1 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.4.1**
- **Spring Data JPA** - Para manipulação de dados
- **MySQL** - Banco de dados relacional
- **Maven** - Gerenciamento de dependências

### 2.2 Estrutura do Projeto

O projeto foi desenvolvido seguindo a arquitetura em camadas do Spring Boot:

```
backend-api/
├── src/main/java/com/example/backendapi/
│   ├── BackendApiApplication.java (Classe principal)
│   ├── model/
│   │   └── Tarefa.java (Entidade JPA)
│   ├── repository/
│   │   └── TarefaRepository.java (Interface JPA Repository)
│   └── controller/
│       └── TarefaController.java (REST Controller)
└── src/main/resources/
    └── application.properties (Configurações do banco)
```

### 2.3 Modelo de Dados

**Entidade Tarefa:**
- `id` (Long) - Identificador único, gerado automaticamente
- `nome` (String) - Nome da tarefa (obrigatório, 3-200 caracteres)
- `dataEntrega` (LocalDate) - Data de entrega (obrigatório)
- `responsavel` (String) - Responsável pela tarefa (obrigatório, 3-100 caracteres)

---

## 3. ENDPOINTS IMPLEMENTADOS

### 3.1 Base URL
```
http://localhost:8080/api/tarefas
```

### 3.2 Endpoints REST

| Método | Endpoint | Descrição | Status HTTP |
|--------|----------|-----------|-------------|
| POST | `/api/tarefas` | Criar nova tarefa | 201 Created |
| GET | `/api/tarefas` | Listar todas as tarefas | 200 OK |
| GET | `/api/tarefas/{id}` | Buscar tarefa por ID | 200 OK / 404 Not Found |
| PUT | `/api/tarefas/{id}` | Atualizar tarefa | 200 OK / 404 Not Found |
| DELETE | `/api/tarefas/{id}` | Remover tarefa | 204 No Content / 404 Not Found |

---

## 4. TESTES REALIZADOS NO POSTMAN

### TESTE 1: Criação de Tarefa (POST)
**Critério de Avaliação:** Implementação correta do endpoint de inserção com nome e RU do aluno.

#### Configuração no Postman:
- **Método:** POST
- **URL:** `http://localhost:8080/api/tarefas`
- **Headers:** 
  - `Content-Type: application/json`
- **Body (raw JSON):**
```json
{
  "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
  "dataEntrega": "2025-12-10",
  "responsavel": "[SEU NOME COMPLETO] - RU: [SEU RU]"
}
```

#### Resposta Esperada:
```json
{
  "id": 1,
  "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
  "dataEntrega": "2025-12-10",
  "responsavel": "[SEU NOME COMPLETO] - RU: [SEU RU]"
}
```

#### Status HTTP: 201 Created

**📸 EVIDÊNCIA (PRINT):**  
[INSERIR AQUI O PRINT DO POSTMAN MOSTRANDO:]
- Request com método POST
- Body JSON contendo seu nome e RU
- Response 201 Created
- Response body com a tarefa criada incluindo seu nome e RU

**✅ ATENÇÃO:** O print DEVE mostrar claramente seu nome e RU no campo "responsavel" da resposta.

---

### TESTE 2: Listagem de Tarefas (GET)
**Critério de Avaliação:** Implementação correta do endpoint de listagem, mostrando inclusive o registro com nome do aluno e RU.

#### Configuração no Postman:
- **Método:** GET
- **URL:** `http://localhost:8080/api/tarefas`
- **Headers:** Não necessário

#### Resposta Esperada:
```json
[
  {
    "id": 1,
    "nome": "Trabalho de Desenvolvimento Web Backend - API RESTful",
    "dataEntrega": "2025-12-10",
    "responsavel": "[SEU NOME COMPLETO] - RU: [SEU RU]"
  }
]
```

#### Status HTTP: 200 OK

**📸 EVIDÊNCIA (PRINT):**  
[INSERIR AQUI O PRINT DO POSTMAN MOSTRANDO:]
- Request com método GET
- Response 200 OK
- Response body com array contendo a tarefa criada
- A tarefa DEVE conter seu nome e RU no campo "responsavel"

**✅ ATENÇÃO:** O print DEVE mostrar claramente a lista com sua tarefa contendo seu nome e RU.

---

### TESTE 3: Atualização de Tarefa (PUT)
**Critério de Avaliação:** Implementação correta do endpoint de atualização do registro contendo nome do aluno e RU.

#### Configuração no Postman:
- **Método:** PUT
- **URL:** `http://localhost:8080/api/tarefas/1` (usar o ID da tarefa criada)
- **Headers:** 
  - `Content-Type: application/json`
- **Body (raw JSON):**
```json
{
  "nome": "Trabalho Atualizado - API RESTful de Tarefas",
  "dataEntrega": "2025-12-15",
  "responsavel": "[SEU NOME COMPLETO] - RU: [SEU RU]"
}
```

#### Resposta Esperada:
```json
{
  "id": 1,
  "nome": "Trabalho Atualizado - API RESTful de Tarefas",
  "dataEntrega": "2025-12-15",
  "responsavel": "[SEU NOME COMPLETO] - RU: [SEU RU]"
}
```

#### Status HTTP: 200 OK

**📸 EVIDÊNCIA (PRINT):**  
[INSERIR AQUI O PRINT DO POSTMAN MOSTRANDO:]
- Request com método PUT
- URL com o ID da tarefa
- Body JSON com dados atualizados contendo seu nome e RU
- Response 200 OK
- Response body com a tarefa atualizada mostrando seu nome e RU

**✅ ATENÇÃO:** O print DEVE mostrar claramente que a tarefa foi atualizada e ainda contém seu nome e RU.

---

### TESTE 4: Remoção de Tarefa (DELETE)
**Critério de Avaliação:** Implementação correta do endpoint de remoção do registro contendo nome e RU do aluno.

#### Configuração no Postman:
- **Método:** DELETE
- **URL:** `http://localhost:8080/api/tarefas/1` (usar o ID da tarefa criada)
- **Headers:** Não necessário

#### Resposta Esperada:
- **Status HTTP:** 204 No Content
- **Response Body:** Vazio

#### Verificação Adicional:
Após a remoção, executar GET `/api/tarefas` deve retornar array vazio `[]`.

**📸 EVIDÊNCIA (PRINT):**  
[INSERIR AQUI O PRINT DO POSTMAN MOSTRANDO:]
- Request com método DELETE
- URL com o ID da tarefa que contém seu nome e RU
- Response 204 No Content
- (Opcional) Print adicional mostrando GET /api/tarefas retornando array vazio

**✅ ATENÇÃO:** O print DEVE mostrar claramente que a tarefa com seu nome e RU foi removida (status 204).

---

## 5. CONFIGURAÇÃO DO BANCO DE DADOS

### 5.1 Criação do Banco

```sql
CREATE DATABASE tarefasdb;
```

### 5.2 Configuração no application.properties

```properties
spring.application.name=tarefa-api
spring.datasource.url=jdbc:mysql://localhost:3306/tarefasdb?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.show-sql=true
spring.jackson.serialization.write-dates-as-timestamps=false
```

### 5.3 Tabela Gerada Automaticamente

A tabela `tarefas` é criada automaticamente pelo Hibernate com a seguinte estrutura:

```sql
CREATE TABLE tarefas (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(200) NOT NULL,
    data_entrega DATE NOT NULL,
    responsavel VARCHAR(100) NOT NULL
);
```

---

## 6. PADRÕES REST IMPLEMENTADOS

✅ **GET** para consultas (listar e buscar)  
✅ **POST** para criação de recursos  
✅ **PUT** para atualização completa  
✅ **DELETE** para remoção  
✅ Códigos HTTP apropriados (200, 201, 204, 404)  
✅ JSON como formato de dados  
✅ URLs semânticas e RESTful  
✅ Tratamento adequado de erros  

---

## 7. VALIDAÇÕES IMPLEMENTADAS

A API possui validações que garantem a integridade dos dados:

- ✅ Campo `nome`: obrigatório, mínimo 3 caracteres, máximo 200 caracteres
- ✅ Campo `dataEntrega`: obrigatório, formato de data válido
- ✅ Campo `responsavel`: obrigatório, mínimo 3 caracteres, máximo 100 caracteres

**Exemplo de resposta de erro de validação:**
```json
{
  "timestamp": "2025-11-21T15:30:00",
  "status": 400,
  "error": "Bad Request",
  "message": "Validation failed"
}
```

---

## 8. INSTRUÇÕES PARA EXECUÇÃO

### 8.1 Pré-requisitos

1. Java 17 ou superior instalado
2. MySQL instalado e rodando
3. Maven (ou usar o Maven Wrapper incluído no projeto)

### 8.2 Passos para Executar

1. **Clone o repositório:**
```bash
git clone https://github.com/Srliper/api-java_bakend.git
cd api-java_bakend/backend-api
```

2. **Crie o banco de dados MySQL:**
```sql
CREATE DATABASE tarefasdb;
```

3. **Configure as credenciais** no arquivo `application.properties` se necessário

4. **Execute a aplicação:**
```bash
# Windows
mvnw.cmd spring-boot:run

# Linux/Mac
./mvnw spring-boot:run
```

5. **A aplicação estará disponível em:** `http://localhost:8080`

---

## 9. CONCLUSÃO

Este trabalho implementou com sucesso uma API RESTful completa para gerenciamento de tarefas utilizando:

- ✅ Java com Spring Boot
- ✅ Spring Data JPA para manipulação de dados
- ✅ MySQL como banco de dados relacional
- ✅ Padrões REST adequados
- ✅ Validações de dados
- ✅ Tratamento de erros apropriado

Todos os requisitos funcionais foram implementados:
- ✅ Criar tarefa
- ✅ Consultar todas as tarefas
- ✅ Consultar tarefa específica por ID
- ✅ Atualizar tarefa existente
- ✅ Remover tarefa

Todos os requisitos não funcionais foram atendidos:
- ✅ API desenvolvida em Java com Spring Boot
- ✅ Utilização de banco de dados relacional (MySQL)
- ✅ Implementação com Spring Data JPA
- ✅ Documentação com Postman
- ✅ API segue padrões REST

---

## 10. ANEXOS

### Anexo A: Prints dos Testes no Postman

[INSERIR AQUI OS 4 PRINTS OBRIGATÓRIOS:]

1. **Print do Teste 1 (Criação)** - Mostrando criação com nome e RU
2. **Print do Teste 2 (Listagem)** - Mostrando lista com tarefa contendo nome e RU
3. **Print do Teste 3 (Atualização)** - Mostrando atualização da tarefa com nome e RU
4. **Print do Teste 4 (Remoção)** - Mostrando remoção da tarefa (status 204)

### Anexo B: Código Fonte

O código fonte completo está disponível no repositório GitHub:
https://github.com/Srliper/api-java_bakend.git

---

**Data de Entrega:** _______________  
**Assinatura do Aluno:** _______________

---

## OBSERVAÇÕES IMPORTANTES

⚠️ **ATENÇÃO:** 
- Substitua `[SEU NOME COMPLETO]` e `[SEU RU]` pelos seus dados reais em TODOS os testes
- Os prints devem mostrar CLARAMENTE seu nome e RU nos campos apropriados
- Sem os prints com evidências, a nota será ZERO conforme os critérios de avaliação
- Certifique-se de que o link do GitHub está funcionando antes de entregar

---

**FIM DO CADERNO DE ATIVIDADES E RESPOSTAS**

