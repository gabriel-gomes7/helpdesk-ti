# API

## Objetivo

A API do HelpDesk TI será responsável pela comunicação entre o Front-end e o Back-end através de uma arquitetura REST, permitindo o gerenciamento completo dos chamados de suporte.

Todas as requisições e respostas utilizarão o formato JSON.

---

# Padrões

## URL Base

```
/api/v1
```

---

## Formato de Dados

Todas as requisições e respostas deverão utilizar JSON.

Exemplo:

```json
{
  "message": "Success"
}
```

---

## Convenções da API

- Todas as respostas serão retornadas em formato JSON.
- Todos os endpoints utilizarão substantivos no plural.
- Os IDs serão numéricos.
- Datas serão retornadas no padrão ISO 8601.
- As mensagens retornadas pela API serão em português.
- O versionamento será realizado através da URL (`/api/v1`).

---

## Códigos HTTP

| Código | Descrição |
|---------|-----------|
| 200 | OK |
| 201 | Created |
| 400 | Bad Request |
| 404 | Not Found |
| 500 | Internal Server Error |

---

# Endpoints

## Tickets

### Criar chamado

**POST** `/api/v1/tickets`

Descrição:

Cria um novo chamado.

Body:

```json
{
  "name": "Gabriel Gomes",
  "email": "gabriel@empresa.com",
  "department_id": 1,
  "category_id": 2,
  "description": "O computador não liga."
}
```

Resposta:

```json
{
  "success": true,
  "message": "Chamado criado com sucesso.",
  "data": {
    "ticket_number": "CH-000001"
  }
}
```

---

### Listar chamados

**GET** `/api/v1/tickets`

Descrição:

Retorna todos os chamados cadastrados.

Parâmetros opcionais:

| Parâmetro | Descrição |
|-----------|-----------|
| page | Página |
| limit | Quantidade por página |
| status | Filtrar por status |
| priority | Filtrar por prioridade |
| department | Filtrar por setor |
| category | Filtrar por categoria |
| sort | Campo de ordenação |
| order | asc ou desc |

Exemplo:

```
GET /api/v1/tickets?page=1&limit=20
```

---

### Buscar chamado pelo ID

**GET** `/api/v1/tickets/{id}`

Descrição:

Retorna os detalhes de um chamado utilizando o ID interno.

---

### Buscar chamado pelo número

**GET** `/api/v1/tickets/number/{ticket_number}`

Descrição:

Retorna um chamado através do número de identificação.

Exemplo:

```
GET /api/v1/tickets/number/CH-000001
```

---

### Pesquisar chamados

**GET** `/api/v1/tickets/search?q=texto`

Descrição:

Pesquisa chamados por número, colaborador ou descrição.

Exemplo:

```
GET /api/v1/tickets/search?q=impressora
```

---

### Editar chamado

**PUT** `/api/v1/tickets/{id}`

Descrição:

Atualiza as informações do chamado.

---

### Alterar prioridade

**PATCH** `/api/v1/tickets/{id}/priority`

Body:

```json
{
  "priority_id": 3
}
```

---

### Alterar status

**PATCH** `/api/v1/tickets/{id}/status`

Body:

```json
{
  "status_id": 2
}
```

---

### Atualizar observações técnicas

**PATCH** `/api/v1/tickets/{id}/notes`

Body:

```json
{
  "technician_notes": "Equipamento em análise."
}
```

---

### Encerrar chamado

**PATCH** `/api/v1/tickets/{id}/close`

Body:

```json
{
  "resolution_notes": "Fonte substituída e equipamento testado."
}
```

---

### Reabrir chamado

**PATCH** `/api/v1/tickets/{id}/reopen`

Descrição:

Reabre um chamado previamente encerrado.

---

## Requesters

### Listar colaboradores

**GET** `/api/v1/requesters`

---

### Buscar colaborador

**GET** `/api/v1/requesters/{id}`

---

### Listar chamados do colaborador

**GET** `/api/v1/requesters/{id}/tickets`

---

## Departments

### Listar departamentos

**GET** `/api/v1/departments`

---

## Categories

### Listar categorias

**GET** `/api/v1/categories`

---

## Priorities

### Listar prioridades

**GET** `/api/v1/priorities`

---

## Statuses

### Listar status

**GET** `/api/v1/statuses`

---

# Estrutura das Respostas

## Sucesso

```json
{
  "success": true,
  "message": "Operação realizada com sucesso.",
  "data": {}
}
```

---

## Erro

```json
{
  "success": false,
  "message": "Descrição do erro."
}
```

---

# Validações

A API deverá validar:

- Campos obrigatórios;
- Formato do e-mail;
- Existência do colaborador;
- Existência do departamento;
- Existência da categoria;
- Existência da prioridade;
- Existência do status;
- Campos vazios;
- Tipos de dados enviados.

---

# Versionamento

Todas as rotas utilizarão versionamento através da URL.

Exemplo:

```
/api/v1
```

Novas versões poderão ser disponibilizadas futuramente sem comprometer a compatibilidade com aplicações existentes.