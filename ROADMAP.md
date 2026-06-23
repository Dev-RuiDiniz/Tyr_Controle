# ROADMAP.md - Roadmap de Desenvolvimento

**Projeto:** Tyr_Controle  
**Atualizado em:** 2026-06-23  
**Metodologia:** Specification-Driven Development (SDD) + Test-Driven Development (TDD)  

---

## 1. Visao Geral

O projeto sera desenvolvido em fases, epicos, historias e tarefas. Cada funcionalidade deve iniciar com especificacao, criterios de aceite e desenho tecnico antes da implementacao. O ciclo de entrega deve seguir TDD: RED, GREEN e REFACTOR.

## 2. Convencoes de Status

- `PENDENTE`
- `EM ESPECIFICACAO`
- `ESPECIFICADO`
- `EM TESTE`
- `EM DESENVOLVIMENTO`
- `EM REVISAO`
- `CONCLUIDO`
- `BLOQUEADO`
- `CANCELADO`

## 3. Fases do Projeto

### Fase 0 - Governanca e Stack

**Objetivo:** documentar o projeto, definir stack e padroes de trabalho.

Epicos:

- EP-0001 - Criar governanca do repositorio.
- EP-0002 - Definir stack oficial.
- EP-0003 - Mapear escopo funcional.
- EP-0004 - Definir roadmap SDD/TDD.

Criterios de aceite:

- [x] Stack definida.
- [x] `AGENTS.md` criado.
- [x] `ARQUITETURA.md` criado.
- [x] `BANCO_DADOS.md` criado.
- [x] `ESCOPO.md` criado.
- [x] `ROADMAP.md` criado.
- [x] `CONTEXTO.md` criado.
- [x] `RELATORIO.md` criado.

### Fase 1 - Base Tecnica e Ambiente

**Objetivo:** criar a aplicacao Next.js e configurar a base tecnica.

Tarefas:

- [ ] Inicializar Next.js com TypeScript e App Router.
- [ ] Configurar Tailwind CSS.
- [ ] Configurar shadcn/ui e lucide-react.
- [ ] Configurar ESLint, Prettier e TypeScript strict.
- [ ] Configurar Vitest e React Testing Library.
- [ ] Configurar Playwright.
- [ ] Configurar Supabase.
- [ ] Configurar Prisma.
- [ ] Configurar variaveis de ambiente sem expor secrets.
- [ ] Validar `npm run dev`, `npm run lint`, `npm run test` e `npm run build`.

### Fase 2 - Autenticacao, Usuarios e RBAC

#### Historia: Acessar o painel com perfil autorizado

- **Como:** usuario do sistema.
- **Quero:** autenticar e acessar apenas areas permitidas.
- **Para:** proteger dados de projetos e clientes.
- **Status:** PENDENTE.

##### SDD

- Especificacao: login/logout com Supabase Auth e perfis RBAC.
- Criterios de aceite: usuario autenticado acessa painel; usuario sem permissao recebe bloqueio; sessao e validada server-side.
- Impacto tecnico: Supabase Auth, middleware, layout protegido, tabela de perfil e politicas RLS.

##### TDD

- Teste RED: rota protegida bloqueia usuario anonimo.
- GREEN: implementar protecao minima.
- Refatoracao: extrair helpers de sessao e autorizacao.
- Regressao: garantir que cliente nao veja projeto nao autorizado.

### Fase 3 - Cadastros Core

Epicos:

- EP-0005 - Usuarios e perfis.
- EP-0006 - Desenvolvedores.
- EP-0007 - Projetos.
- EP-0008 - Membros do projeto.

Tarefas:

- [ ] Especificar schemas Zod.
- [ ] Criar migrations Prisma.
- [ ] Criar telas de listagem e formulario.
- [ ] Criar Server Actions.
- [ ] Criar testes unitarios e integrados.
- [ ] Validar permissoes por perfil.

### Fase 4 - Gestao de Projeto

Epicos:

- EP-0009 - Escopos.
- EP-0010 - Roadmaps.
- EP-0011 - Marcos.
- EP-0012 - Tarefas e backlog.
- EP-0013 - Prazos e impedimentos.

Cada epico deve seguir o formato:

```markdown
#### Historia: [nome]
- Como: [perfil]
- Quero: [acao]
- Para: [beneficio]
- Status: PENDENTE

##### SDD
- Especificacao:
- Criterios de aceite:
- Impacto tecnico:

##### TDD
- Teste RED:
- Implementacao GREEN:
- Refatoracao:
- Teste de regressao:
```

### Fase 5 - Dashboard e Relatorios

**Objetivo:** entregar indicadores de acompanhamento e relatorios simples.

Tarefas:

- [ ] Definir KPIs do dashboard.
- [ ] Criar consultas agregadas.
- [ ] Criar graficos com Recharts.
- [ ] Criar relatorio simples por projeto.
- [ ] Testar filtros e permissoes.

### Fase 6 - Funcionalidades Avancadas

Epicos futuros:

- EP-0014 - Kanban visual.
- EP-0015 - Portal do cliente.
- EP-0016 - Aprovacoes.
- EP-0017 - Mudancas de escopo.
- EP-0018 - Notificacoes.
- EP-0019 - Relatorios PDF/Excel.
- EP-0020 - Integracoes com GitHub/GitLab.
- EP-0021 - Recursos de IA.

### Fase 7 - Deploy, Observabilidade e Operacao

Tarefas:

- [ ] Configurar projeto na Vercel.
- [ ] Configurar variaveis de ambiente.
- [ ] Configurar Supabase producao.
- [ ] Validar build em ambiente remoto.
- [ ] Documentar deploy e rollback.
- [ ] Configurar observabilidade inicial.

## 4. Backlog Geral

| ID | Tipo | Descricao | Prioridade | Status |
|---|---|---|---|---|
| EP-0001 | Documentacao | Criar governanca do repositorio | Alta | CONCLUIDO |
| EP-0002 | Arquitetura | Definir stack oficial | Alta | CONCLUIDO |
| EP-0005 | Epico | Usuarios e perfis | Alta | PENDENTE |
| EP-0006 | Epico | Desenvolvedores | Alta | PENDENTE |
| EP-0007 | Epico | Projetos | Alta | PENDENTE |
| EP-0009 | Epico | Escopos | Alta | PENDENTE |
| EP-0012 | Epico | Tarefas e backlog | Alta | PENDENTE |
| EP-0014 | Epico | Kanban visual | Media | PENDENTE |
| EP-0021 | Epico | Recursos de IA | Baixa | PENDENTE |

## 5. Matriz SDD/TDD por Tarefa

| ID | Tarefa | Spec criada | Teste criado | Implementado | Documentado |
|---|---|---|---|---|---|
| DOC-001 | Governanca do repositorio | Sim | N/A | Sim | Sim |
| STACK-001 | Definicao da stack | Sim | N/A | Sim | Sim |
| APP-001 | Bootstrap Next.js | Nao | Nao | Nao | Parcial |
| AUTH-001 | Login com Supabase | Nao | Nao | Nao | Parcial |
| DB-001 | Schema Prisma inicial | Nao | Nao | Nao | Parcial |

## 6. Definicao de Pronto

Uma tarefa so e considerada pronta quando:

- [ ] Requisito documentado.
- [ ] Criterios de aceite definidos.
- [ ] Teste criado ou justificativa registrada.
- [ ] Implementacao concluida.
- [ ] Testes passando.
- [ ] Documentacao atualizada.
- [ ] `CONTEXTO.md` atualizado.
- [ ] `RELATORIO.md` atualizado.
