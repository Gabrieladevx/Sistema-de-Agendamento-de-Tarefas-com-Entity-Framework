# Sistema de Agendamento de Tarefas - API

## Visão Geral
Este é um sistema gerenciador de tarefas desenvolvido com ASP.NET Core 9.0 e Entity Framework Core, utilizando SQLite como banco de dados.

## Endpoints Disponíveis

### 1. Criar Tarefa
**POST** `/Tarefa`

Corpo da requisição:
```json
{
  "titulo": "Minha primeira tarefa",
  "descricao": "Descrição detalhada da tarefa",
  "data": "2025-07-23T15:30:00.000Z",
  "status": "Pendente"
}
```

Status possíveis: `Pendente` ou `Finalizado`

### 2. Buscar Tarefa por ID
**GET** `/Tarefa/{id}`

Exemplo: `GET /Tarefa/1`

### 3. Listar Todas as Tarefas
**GET** `/Tarefa/ObterTodos`

### 4. Buscar Tarefas por Título
**GET** `/Tarefa/ObterPorTitulo?titulo={texto}`

Exemplo: `GET /Tarefa/ObterPorTitulo?titulo=primeira`

### 5. Buscar Tarefas por Data
**GET** `/Tarefa/ObterPorData?data={data}`

Exemplo: `GET /Tarefa/ObterPorData?data=2025-07-23`

### 6. Buscar Tarefas por Status
**GET** `/Tarefa/ObterPorStatus?status={status}`

Exemplo: `GET /Tarefa/ObterPorStatus?status=Pendente`

### 7. Atualizar Tarefa
**PUT** `/Tarefa/{id}`

Corpo da requisição:
```json
{
  "titulo": "Tarefa atualizada",
  "descricao": "Nova descrição",
  "data": "2025-07-24T10:00:00.000Z",
  "status": "Finalizado"
}
```

### 8. Deletar Tarefa
**DELETE** `/Tarefa/{id}`

Exemplo: `DELETE /Tarefa/1`

## Como Executar

1. Execute o comando no terminal:
   ```bash
   dotnet run
   ```

2. Acesse o Swagger UI em: `https://localhost:7295/swagger`

3. Use os endpoints para gerenciar suas tarefas!

## Banco de Dados
O sistema utiliza SQLite com arquivo `tarefas.db` criado automaticamente na raiz do projeto.

## Estrutura da Tarefa
```json
{
  "id": 1,
  "titulo": "string",
  "descricao": "string", 
  "data": "2025-07-23T15:30:00.000Z",
  "status": "Pendente" // ou "Finalizado"
}
```

## Funcionalidades Implementadas
✅ CRUD completo de tarefas
✅ Busca por ID, título, data e status
✅ Validação de dados
✅ Banco de dados SQLite
✅ Documentação automática com Swagger
✅ Migrations do Entity Framework
