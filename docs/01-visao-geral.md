# Visão Geral

## Sobre o projeto

O HelpDesk TI é um sistema web desenvolvido para centralizar e organizar o atendimento de chamados internos de Tecnologia da Informação.

O projeto surgiu da necessidade de substituir solicitações realizadas por aplicativos de mensagens, como o WhatsApp, por um fluxo estruturado de abertura, acompanhamento e gerenciamento de chamados.

Seu objetivo é oferecer uma ferramenta simples, rápida e intuitiva para colaboradores registrarem problemas técnicos e para o técnico de TI gerenciar todo o ciclo de atendimento.

---

## Objetivo

Desenvolver uma plataforma web que permita:

- Abertura de chamados pelos colaboradores;
- Gerenciamento dos chamados pelo técnico de TI;
- Organização do histórico de atendimentos;
- Controle de status e prioridade;
- Evolução contínua do sistema através de novas funcionalidades.

---

## Público-alvo

### Colaboradores

Responsáveis por registrar solicitações de suporte.

Na versão inicial poderão:

- Informar nome;
- Informar e-mail corporativo;
- Selecionar o setor;
- Selecionar a categoria do problema;
- Descrever o ocorrido;
- Enviar o chamado.

---

### Técnico de TI

Responsável pelo gerenciamento dos atendimentos.

Na versão inicial poderá:

- Visualizar chamados;
- Alterar status;
- Definir prioridade;
- Registrar observações técnicas;
- Encerrar chamados.

---

## Problema que o sistema resolve

Atualmente, muitas solicitações de suporte são realizadas por aplicativos de mensagens, dificultando:

- Organização dos atendimentos;
- Priorização das demandas;
- Histórico de chamados;
- Controle do tempo de atendimento;
- Consulta de problemas recorrentes.

O HelpDesk TI centraliza todas essas informações em um único sistema.

---

## Escopo da versão 1.0

A primeira versão (MVP) terá como foco disponibilizar uma plataforma funcional para abertura e gerenciamento de chamados.

Recursos previstos:

- Cadastro de chamados;
- Listagem de chamados;
- Alteração de status;
- Alteração de prioridade;
- Encerramento de chamados;
- Dashboard simples.

Recursos como autenticação completa, anexos, inventário, notificações por e-mail e múltiplos técnicos serão implementados em versões futuras.

---

## Tecnologias previstas

### Front-end

- React
- Vite
- React Router

### Back-end

- Node.js
- Express

### Banco de Dados

- PostgreSQL

### Hospedagem

- Vercel
- Render
- Supabase

---

## Arquitetura

O projeto será dividido em três partes:

- Front-end
- Back-end
- Banco de Dados

A comunicação ocorrerá através de uma API REST utilizando requisições HTTP.

---

## Objetivos futuros

Após a conclusão da versão 1.0, o projeto poderá evoluir com funcionalidades como:

- Login de usuários;
- Múltiplos técnicos;
- Inventário de equipamentos;
- Upload de imagens;
- Histórico completo de atendimentos;
- Dashboard avançado;
- Notificações por e-mail;
- Base de conhecimento;
- Relatórios.

## Arquitetura da Solução

O HelpDesk TI será desenvolvido utilizando uma arquitetura cliente-servidor, separando a aplicação em três camadas principais: Front-end, Back-end e Banco de Dados.

### Front-end

Aplicação web desenvolvida em React responsável pela interface utilizada pelos colaboradores e pelo técnico de TI.

Suas responsabilidades incluem:

- Exibir a interface do sistema;
- Validar dados informados pelo usuário;
- Consumir a API do Back-end;
- Apresentar os chamados e suas informações.

### Back-end

API REST desenvolvida em Node.js com Express.

Suas responsabilidades incluem:

- Receber requisições do Front-end;
- Validar regras de negócio;
- Gerenciar os chamados;
- Comunicar-se com o banco de dados;
- Retornar respostas para a aplicação.

### Banco de Dados

Banco de dados PostgreSQL responsável pelo armazenamento permanente das informações do sistema.

Serão armazenados dados como:

- Chamados;
- Status;
- Prioridades;
- Categorias;
- Setores;
- Datas de abertura e encerramento.

### Fluxo da Aplicação

O fluxo básico de funcionamento do sistema será:

1. O colaborador acessa o formulário de abertura de chamados.
2. Os dados são enviados ao Back-end através da API.
3. O Back-end valida e registra o chamado no banco de dados.
4. O banco retorna a confirmação do cadastro.
5. O Back-end responde ao Front-end.
6. O colaborador recebe a confirmação da abertura do chamado.
7. O técnico visualiza o novo chamado no painel administrativo.
8. O técnico realiza o atendimento e atualiza o status até a conclusão do chamado.

### Arquitetura Geral

```text
+----------------------+
|     Colaborador      |
+----------+-----------+
           |
           | HTTP
           ▼
+----------------------+
| Front-end (React)    |
+----------+-----------+
           |
           | API REST
           ▼
+----------------------+
| Back-end (Node.js)   |
+----------+-----------+
           |
           | SQL
           ▼
+----------------------+
| PostgreSQL           |
+----------+-----------+
           ▲
           |
+----------+-----------+
| Painel do Técnico    |
+----------------------+
```

Essa arquitetura permite que cada componente seja desenvolvido de forma independente, facilitando a manutenção, a escalabilidade e futuras implementações de novas funcionalidades.