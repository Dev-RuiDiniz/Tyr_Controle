# CONTEXTO.md - Contexto Vivo do Projeto

**Projeto:** Tyr_Controle  
**Atualizado em:** 2026-06-23  
**Responsavel pela atualizacao:** Agente IA  

---

## 1. Resumo Executivo

Tyr_Controle sera uma plataforma web para acompanhamento de projetos de software. O projeto esta em fase inicial de governanca, definicao de stack e planejamento do MVP.

A stack oficial definida e Next.js full-stack com TypeScript, Supabase + PostgreSQL, Prisma e Vercel. O principal objetivo tecnico imediato e criar a base da aplicacao com autenticacao, RBAC, banco versionado e testes.

## 2. Estado Atual do Projeto

| Area | Status | Observacoes |
|---|---|---|
| Backend | Planejado | Next.js Server Actions e Route Handlers |
| Frontend | Planejado | Next.js App Router, React, Tailwind e shadcn/ui |
| Banco de dados | Planejado | Supabase PostgreSQL com Prisma |
| Testes | Planejado | Vitest, React Testing Library e Playwright |
| Infraestrutura | Planejada | Vercel e Supabase |
| Documentacao | Criada | Governanca inicial criada em 2026-06-23 |

## 3. Historico de Desenvolvimento

### 2026-06-23 - Criacao da governanca e definicao de stack

- O que foi analisado: prompt de governanca, escopo do projeto, README e estrutura atual do repositorio.
- O que foi decidido: usar Next.js full-stack, TypeScript, Supabase, PostgreSQL, Prisma, Tailwind, shadcn/ui, Vercel, Vitest e Playwright.
- O que foi criado: `AGENTS.md`, `ARQUITETURA.md`, `BANCO_DADOS.md`, `ESCOPO.md`, `ROADMAP.md`, `CONTEXTO.md` e `RELATORIO.md`.
- O que foi alterado: nenhum codigo funcional.
- O que ficou pendente: bootstrap da aplicacao Next.js, configuracao Supabase, schema Prisma, testes e deploy.
- Evidencias no repositorio: arquivos de governanca na raiz.

## 4. Decisoes Tecnicas e Arquiteturais

| Data | Decisao | Motivo | Impacto | Status |
|---|---|---|---|---|
| 2026-06-23 | Next.js full-stack com TypeScript | Reduzir complexidade do MVP | Frontend e backend no mesmo projeto | Definida |
| 2026-06-23 | Supabase + PostgreSQL | Acelerar auth, banco e storage | Requer RLS e configuracao segura | Definida |
| 2026-06-23 | Prisma | Schema versionado e DX consistente | Migrations via Prisma | Definida |
| 2026-06-23 | Vercel | Deploy natural para Next.js | Infra inicial simplificada | Definida |
| 2026-06-23 | TDD com Vitest e Playwright | Reduzir regressao | Testes desde as primeiras features | Definida |

## 5. Decisoes de Produto e Escopo

| Data | Decisao | Motivo | Impacto |
|---|---|---|---|
| 2026-06-23 | MVP sera web/admin responsivo | Atender gestores, devs e clientes rapidamente | Mobile nativo fica fora do MVP |
| 2026-06-23 | Integracoes externas ficam para fases futuras | Reduzir risco inicial | GitHub, IA e notificacoes entram no roadmap futuro |

## 6. Pendencias Atuais

| Pendencia | Area | Prioridade | Proxima acao |
|---|---|---|---|
| Criar aplicacao Next.js | Frontend/backend | Alta | Executar bootstrap da stack |
| Configurar Supabase | Auth/banco | Alta | Criar projeto e variaveis |
| Criar schema Prisma | Banco | Alta | Especificar modelo inicial |
| Definir RLS | Seguranca | Alta | Criar politicas por perfil |
| Configurar testes | Qualidade | Alta | Instalar Vitest e Playwright |
| Configurar deploy | Infra | Media | Criar projeto Vercel |

## 7. Bloqueios

| Bloqueio | Severidade | Descricao | Dependencia |
|---|---|---|---|
| Nenhum bloqueio tecnico atual | Baixa | Projeto esta em fase de planejamento | N/A |

## 8. Riscos Tecnicos

| Risco | Impacto | Mitigacao |
|---|---|---|
| Escopo amplo | Atraso no MVP | Priorizar fases e epicos essenciais |
| RBAC incompleto | Acesso indevido | Especificar perfis antes dos CRUDs |
| RLS ausente | Vazamento de dados | Habilitar RLS desde a primeira migration |
| Falta de testes | Regressao | Aplicar TDD nos epicos |

## 9. Proximos Passos

1. Inicializar aplicacao Next.js com TypeScript e App Router.
2. Configurar Tailwind, shadcn/ui, ESLint, Prettier e testes.
3. Configurar Prisma e Supabase.
4. Especificar e implementar Auth/RBAC.
5. Criar schema inicial do banco.

## 10. Notas para Proximos Agentes

- Sempre ler este arquivo antes de trabalhar.
- Sempre atualizar este arquivo ao final da sessao.
- Nao remover historico antigo.
- Nao expor credenciais Supabase ou Vercel.
- Registrar decisoes, bloqueios e mudancas de direcao.
