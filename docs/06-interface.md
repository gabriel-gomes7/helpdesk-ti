# Interface

## Objetivo

Este documento define o padrão visual e a experiência de uso do HelpDesk TI.

O objetivo é garantir uma interface moderna, intuitiva, consistente e de fácil utilização tanto para colaboradores quanto para técnicos.

---

# Identidade Visual

## Paleta de Cores

| Elemento | Cor |
|----------|------|
| Fundo Principal | #0D1117 |
| Cards | #161B22 |
| Bordas | #30363D |
| Texto Principal | #E6EDF3 |
| Texto Secundário | #8B949E |
| Botão Primário | #238636 |
| Hover | #2EA043 |
| Erro | #DA3633 |
| Aviso | #D29922 |
| Informação | #1F6FEB |

---

## Tipografia

### Interface

Inter

---

### IDs e Informações Técnicas

JetBrains Mono

---

# Ícones

Os ícones deverão utilizar a biblioteca:

Lucide React

---

# Layout

O sistema utilizará layout administrativo com barra lateral fixa.

Estrutura:

```text
+-------------------------------------------------------------+
| Header                                                      |
+-------------+-----------------------------------------------+
|             |                                               |
|             |                                               |
| Sidebar     |              Conteúdo                         |
|             |                                               |
|             |                                               |
+-------------+-----------------------------------------------+
```

---

# Header

O cabeçalho deverá conter:

- Logo
- Nome do sistema
- Versão
- Usuário logado (V2.0)

---

# Sidebar

Itens disponíveis:

- Dashboard
- Chamados
- Configurações (V2.0)

---

# Telas

## Dashboard

Apresentará:

- Total de chamados
- Chamados abertos
- Em atendimento
- Aguardando usuário
- Fechados

Também deverá exibir:

- Últimos chamados
- Chamados prioritários

---

## Lista de Chamados

A tela deverá apresentar:

- Número
- Colaborador
- Setor
- Categoria
- Prioridade
- Status
- Data de abertura

Também deverá possuir:

- Pesquisa
- Paginação
- Ordenação
- Filtros

---

## Detalhes do Chamado

Informações:

- Número
- Nome
- E-mail
- Setor
- Categoria
- Descrição
- Prioridade
- Status
- Observações técnicas
- Resolução
- Datas

Ações:

- Editar
- Alterar prioridade
- Alterar status
- Encerrar
- Reabrir

---

## Abrir Chamado

Campos:

- Nome
- E-mail
- Setor
- Categoria
- Descrição

Botão:

Enviar chamado

---

# Componentes

## Botões

Primário

Verde

Secundário

Cinza

Perigo

Vermelho

---

## Cards

Todos os cards deverão possuir:

- Borda arredondada
- Fundo escuro
- Borda discreta
- Espaçamento interno

---

## Inputs

Todos os campos deverão possuir:

- Label
- Placeholder
- Mensagem de erro
- Destaque ao receber foco

---

## Tabelas

As tabelas deverão possuir:

- Cabeçalho fixo
- Hover nas linhas
- Paginação
- Ordenação

---

## Modais

Utilizados para:

- Encerrar chamado
- Reabrir chamado
- Confirmar ações

---

## Toasts

Notificações rápidas para:

- Sucesso
- Erro
- Aviso
- Informação

---

# Responsividade

Desktop:

Layout completo.

Tablet:

Sidebar recolhível.

Mobile:

Menu lateral oculto.

---

# Acessibilidade

O sistema deverá:

- Possuir contraste adequado.
- Ser totalmente navegável por teclado.
- Exibir foco nos componentes.
- Utilizar textos legíveis.
- Possuir labels em todos os campos.

---

# Padrões de Interface

- Utilizar espaçamento consistente.
- Evitar excesso de informações.
- Priorizar ações principais.
- Manter consistência visual entre todas as telas.
- Utilizar animações discretas.

---

# Evolução Prevista

Versões futuras poderão incluir:

- Tema claro.
- Upload de imagens.
- Timeline do chamado.
- Dashboard avançado.
- Gráficos.
- Chat interno.
- Notificações em tempo real.