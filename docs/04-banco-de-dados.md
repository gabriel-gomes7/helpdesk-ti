# Banco de Dados

## Objetivo

O banco de dados do HelpDesk TI será responsável por armazenar todas as informações necessárias para o funcionamento do sistema, garantindo integridade, organização e facilidade de manutenção.

Nesta primeira versão (V1.0), o banco foi projetado para atender exclusivamente ao gerenciamento de chamados internos de TI.

---

# Padrão de Nomenclatura

Para manter consistência em todo o projeto, serão adotadas as seguintes convenções:

- Tabelas em inglês e no plural;
- Colunas em inglês;
- Nomes utilizando o padrão `snake_case`;
- Chave primária nomeada como `id`;
- Chaves estrangeiras seguindo o padrão `<table>_id`;
- Campos de data utilizando `created_at`, `updated_at` e `closed_at`.

Exemplos:

- tickets
- requesters
- departments
- categories
- priorities
- statuses

---

# Diagrama Entidade-Relacionamento (ER)

```text
departments (1)
        │
        ▼
requesters (N)
        │
        ▼
tickets (N)
   │    │    │
   │    │    ├────────► priorities
   │    │
   │    ├─────────────► statuses
   │
   └──────────────────► categories
```

---

# Tabelas da V1.0

## requesters

Armazena os colaboradores que realizam solicitações de suporte.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | BIGSERIAL | ✅ |
| name | VARCHAR(150) | ✅ |
| email | VARCHAR(150) | ✅ |
| department_id | BIGINT | ✅ |
| created_at | TIMESTAMP | ✅ |
| updated_at | TIMESTAMP | ✅ |

---

## departments

Armazena os setores cadastrados no sistema.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | SERIAL | ✅ |
| name | VARCHAR(100) | ✅ |

---

## categories

Armazena as categorias dos chamados.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | SERIAL | ✅ |
| name | VARCHAR(100) | ✅ |

Categorias iniciais:

- Computador
- Notebook
- Impressora
- Sistema
- Internet
- Rede
- Telefone
- E-mail
- Monitor
- Outro

---

## priorities

Armazena os níveis de prioridade.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | SERIAL | ✅ |
| name | VARCHAR(50) | ✅ |

Prioridades iniciais:

- Baixa
- Normal
- Alta
- Urgente

---

## statuses

Armazena os possíveis status dos chamados.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | SERIAL | ✅ |
| name | VARCHAR(50) | ✅ |

Status iniciais:

- Aberto
- Em atendimento
- Aguardando usuário
- Fechado

---

## tickets

Tabela principal do sistema.

Cada registro representa um chamado.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | BIGSERIAL | ✅ |
| ticket_number | VARCHAR(20) | ✅ |
| requester_id | BIGINT | ✅ |
| category_id | BIGINT | ✅ |
| priority_id | BIGINT | ✅ |
| status_id | BIGINT | ✅ |
| description | TEXT | ✅ |
| technician_notes | TEXT | ❌ |
| created_at | TIMESTAMP | ✅ |
| updated_at | TIMESTAMP | ✅ |
| closed_at | TIMESTAMP | ❌ |

---

# Relacionamentos

## requesters

- department_id → departments.id

## tickets

Tabela principal do sistema.

Cada registro representa um chamado.

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | BIGSERIAL | ✅ |
| ticket_number | VARCHAR(20) | ✅ |
| requester_id | BIGINT | ✅ |
| category_id | BIGINT | ✅ |
| priority_id | BIGINT | ✅ |
| status_id | BIGINT | ✅ |
| description | TEXT | ✅ |
| technician_notes | TEXT | ❌ |
| resolution_notes | TEXT | ❌ |
| created_at | TIMESTAMP | ✅ |
| updated_at | TIMESTAMP | ✅ |
| closed_at | TIMESTAMP | ❌ |
---

# Regras de Integridade

- Todo colaborador pertence a um setor.
- Todo chamado pertence a um colaborador.
- Todo chamado pertence a uma categoria.
- Todo chamado possui uma prioridade.
- Todo chamado possui um status.
- O número do chamado (ticket_number) deve ser único.
- O número do chamado (ticket_number) deve ser único e nunca poderá ser reutilizado.
- A data de abertura é gerada automaticamente.
- A data de atualização é alterada automaticamente sempre que houver modificações.
- A data de encerramento somente será preenchida quando o chamado for finalizado.

---

# Dados Iniciais (Seed)

O sistema deverá criar automaticamente os seguintes registros na primeira execução:

## Prioridades

- Baixa
- Normal
- Alta
- Urgente

## Status

- Aberto
- Em atendimento
- Aguardando usuário
- Fechado

## Categorias

- Computador
- Notebook
- Impressora
- Sistema
- Internet
- Rede
- Telefone
- E-mail
- Monitor
- Outro

## Setores

Os setores não serão pré-definidos no projeto.

Cada empresa poderá cadastrar seus próprios departamentos conforme sua estrutura organizacional.

---

# Evolução Prevista

A estrutura do banco foi planejada para permitir futuras expansões sem necessidade de grandes alterações estruturais.

Funcionalidades previstas para versões futuras:

- Cadastro de técnicos;
- Autenticação de usuários;
- Histórico completo de alterações;
- Inventário de equipamentos;
- Cadastro de múltiplas empresas;
- Upload de anexos;
- Notificações por e-mail;
- Dashboard avançado;
- Base de conhecimento.