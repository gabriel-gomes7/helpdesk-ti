# Requisitos

## Objetivo

Este documento define os requisitos funcionais, não funcionais e as regras de negócio do sistema HelpDesk TI.

---

# Requisitos Funcionais

## RF001 - Abrir chamado

O sistema deve permitir que um colaborador abra um chamado informando:

- Nome
- E-mail corporativo
- Setor
- Categoria
- Descrição do problema

---

## RF002 - Gerar número do chamado

Ao cadastrar um chamado, o sistema deverá gerar automaticamente um número único para identificação.

Exemplo:

CH-000001

---

## RF003 - Registrar data de abertura

Todo chamado deverá possuir a data e hora de abertura.

---

## RF004 - Listar chamados

O técnico deverá visualizar todos os chamados cadastrados.

---

## RF005 - Visualizar detalhes

O técnico poderá abrir um chamado para visualizar todas as informações cadastradas.

---

## RF006 - Alterar status

O técnico poderá alterar o status do chamado.

Status disponíveis:

- Aberto
- Em atendimento
- Aguardando usuário
- Fechado

---

## RF007 - Alterar prioridade

O técnico poderá definir a prioridade do chamado.

Prioridades:

- Baixa
- Normal
- Alta
- Urgente

---

## RF008 - Adicionar observação técnica

O técnico poderá registrar observações durante o atendimento.

---

## RF009 - Encerrar chamado

O técnico poderá finalizar um chamado.

Ao finalizar, o sistema deverá registrar automaticamente a data e hora do encerramento.

---

## RF010 - Dashboard

O sistema deverá apresentar um painel contendo:

- Chamados abertos
- Chamados fechados
- Chamados em atendimento
- Chamados aguardando usuário

---

## RF011 - Editar chamado

O técnico poderá editar as informações de um chamado, exceto seu número de identificação e a data de abertura.

---

## RF012 - Reabrir chamado

O técnico poderá reabrir um chamado encerrado quando necessário.

---

# Requisitos Não Funcionais

## RNF001

O sistema deverá possuir interface responsiva.

---

## RNF002

O sistema deverá ser desenvolvido utilizando React no Front-end.

---

## RNF003

O Back-end deverá utilizar Node.js com Express.

---

## RNF004

O banco de dados deverá utilizar PostgreSQL.

---

## RNF005

A comunicação entre Front-end e Back-end deverá ocorrer através de uma API REST.

---

## RNF006

O sistema deverá utilizar Git para controle de versão.

---

## RNF007

O projeto deverá utilizar GitHub como repositório oficial.

---

## RNF008

O código deverá seguir boas práticas de organização, legibilidade e manutenção.

---

## Regras de Negócio

### RN001

Todo chamado deverá possuir um número único.

---

### RN002

Todo chamado deverá iniciar com status **"Aberto"**.

---

### RN003

Todo chamado deverá iniciar com prioridade **"Normal"**.

---

### RN004

A data de abertura será gerada automaticamente pelo sistema.

---

### RN005

A data de encerramento somente será preenchida quando o chamado for fechado.

---

### RN006

Somente o técnico poderá alterar o status, a prioridade e as observações técnicas do chamado.

---

### RN007

Todos os campos do formulário de abertura de chamado são obrigatórios.

---

### RN008

Os setores deverão ser selecionados a partir de uma lista pré-definida.

---

### RN009

As categorias deverão ser selecionadas a partir de uma lista pré-definida.

---

### RN010

O e-mail informado deverá estar em um formato válido.

---

### RN011

O número do chamado deverá ser gerado automaticamente pelo sistema e não poderá ser alterado.

---

### RN012

O número do chamado deverá permanecer único durante toda a vida útil do sistema.

---

### RN013

O sistema deverá registrar automaticamente a data e hora da última atualização de cada chamado.