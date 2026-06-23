# ESCOPO.md - Escopo do Projeto

**Projeto:** Tyr_Controle  
**Atualizado em:** 2026-06-23  
**Fase:** Planejamento / MVP a iniciar  

---

## 1. Objetivo do Projeto

Desenvolver uma plataforma web para acompanhamento de projetos de software, permitindo cadastrar desenvolvedores, projetos, escopos, roadmaps, marcos, tarefas, prazos, entregas, impedimentos, aprovacoes e relatorios.

## 2. Problema que o Sistema Resolve

Equipes de desenvolvimento, gestores e clientes frequentemente perdem visibilidade sobre o andamento real dos projetos. O sistema resolve essa dor ao centralizar informacoes tecnicas, operacionais e executivas em uma plataforma rastreavel.

## 3. Publico-Alvo e Perfis

| Perfil | Descricao | Permissoes |
|---|---|---|
| Administrador | Gerencia todo o sistema | Usuarios, projetos, permissoes, relatorios e configuracoes |
| Gestor de Projeto | Acompanha projetos especificos | Criar/editar projetos atribuidos, roadmaps, marcos, tarefas e relatorios |
| Desenvolvedor | Executa atividades tecnicas | Visualizar projetos atribuidos, atualizar tarefas, registrar progresso e impedimentos |
| Cliente/Visualizador | Acompanha andamento externo | Visualizar projetos autorizados, prazos, roadmap, marcos e relatorios |

Autorizacao alvo: RBAC com Supabase Auth e regras server-side no Next.js.

## 4. Escopo Funcional do MVP

### Autenticacao e Usuarios

- [ ] Login e logout.
- [ ] Controle de sessao.
- [ ] Cadastro de usuarios.
- [ ] Perfis RBAC.
- [ ] Protecao de rotas.

### Desenvolvedores

- [ ] Criar desenvolvedor.
- [ ] Editar dados.
- [ ] Ativar/inativar.
- [ ] Vincular a projetos.
- [ ] Consultar carga e historico.

### Projetos

- [ ] Criar projeto.
- [ ] Editar projeto.
- [ ] Vincular cliente, gestor e equipe.
- [ ] Definir status, prioridade e prazos.
- [ ] Visualizar progresso geral.

### Escopos

- [ ] Criar escopo por projeto.
- [ ] Editar e versionar escopo.
- [ ] Separar por modulos.
- [ ] Marcar itens aprovados.
- [ ] Registrar alteracoes solicitadas.

### Roadmaps e Marcos

- [ ] Criar fases do roadmap.
- [ ] Definir datas e responsaveis.
- [ ] Criar marcos de desenvolvimento.
- [ ] Marcar fases e marcos como concluidos.
- [ ] Registrar atrasos.

### Tarefas, Prazos e Atualizacoes

- [ ] Criar tarefas por projeto.
- [ ] Definir responsavel, prioridade, status e prazo.
- [ ] Registrar comentarios.
- [ ] Registrar impedimentos.
- [ ] Criar atualizacoes periodicas do projeto.

### Dashboard e Relatorios

- [ ] Dashboard com indicadores principais.
- [ ] Relatorio simples do projeto.
- [ ] Indicadores de atraso, progresso e tarefas.

## 5. Escopo Futuro

- Kanban visual.
- Calendario de entregas.
- Portal do cliente.
- Aprovacoes formais.
- Mudancas de escopo com impacto em prazo/custo.
- Relatorios PDF, Excel e CSV.
- Integracao com GitHub/GitLab.
- Notificacoes por e-mail, WhatsApp, Slack ou Discord.
- Controle de horas e financeiro.
- IA para resumos, riscos e proximas tarefas.

## 6. Fora do Escopo Inicial

- Aplicativo mobile nativo.
- Backend separado em FastAPI ou NestJS.
- Integracoes externas obrigatorias no MVP.
- IA em producao no MVP.
- Controle financeiro completo no MVP.
- Assinatura digital no MVP.

## 7. Escopo Nao Funcional

- Seguranca: RBAC, RLS no Supabase, validacao com Zod e secrets fora do client.
- Performance: listagens paginadas e indices nas consultas principais.
- Usabilidade: interface responsiva para uso administrativo.
- Observabilidade: logs e metricas iniciais via Vercel.
- Manutenibilidade: TypeScript strict, Prisma, testes e documentacao viva.
- LGPD: PENDENTE DE VALIDACAO para classificacao de dados pessoais.

## 8. Regras de Negocio

| Codigo | Regra | Modulo | Status |
|---|---|---|---|
| RN-001 | O usuario precisa estar autenticado para acessar o painel | Auth | Definida |
| RN-002 | Um projeto pode ter varios desenvolvedores | Projetos | Definida |
| RN-003 | Um desenvolvedor pode participar de varios projetos | Desenvolvedores | Definida |
| RN-004 | Uma fase pode ter varias tarefas | Roadmap | Definida |
| RN-005 | Uma tarefa deve possuir responsavel | Tarefas | Definida |
| RN-006 | Alteracoes de escopo devem gerar historico | Escopos | Definida |
| RN-007 | Prazos vencidos devem ser destacados | Prazos | Definida |
| RN-008 | Projetos concluidos exigem permissao administrativa para alteracao | Projetos | Definida |
| RN-009 | Clientes veem apenas projetos autorizados | RBAC | Definida |
| RN-010 | Toda alteracao relevante deve ser registrada em auditoria | Auditoria | Definida |

## 9. Criterios Gerais de Aceite

- [ ] Aplicacao Next.js executa localmente.
- [ ] Supabase Auth configurado.
- [ ] Prisma conectado ao PostgreSQL.
- [ ] CRUDs principais do MVP implementados.
- [ ] Testes principais configurados e passando.
- [ ] Banco documentado e migrations rastreaveis.
- [ ] Fluxos principais validados.
- [ ] Sem credenciais expostas.
- [ ] Documentacao atualizada.

## 10. Entregaveis

- Aplicacao web responsiva.
- Sistema de login.
- Painel administrativo.
- Cadastro de usuarios, desenvolvedores e projetos.
- Gestao de escopo, roadmap, marcos e tarefas.
- Controle de prazos.
- Dashboard e relatorios basicos.
- Banco PostgreSQL com migrations.
- Testes unitarios, integrados e E2E.
- Documentacao tecnica e de governanca.
- Deploy na Vercel.

## 11. Premissas

- Stack oficial: Next.js full-stack, TypeScript, Supabase, Prisma e Vercel.
- O produto sera SaaS/admin web responsivo.
- O MVP prioriza gestao de projetos e acompanhamento operacional.
- Integracoes avancadas serao epicos futuros.

## 12. Riscos

| Risco | Impacto | Probabilidade | Mitigacao |
|---|---|---|---|
| Escopo amplo demais para MVP | Atraso | Alta | Priorizar funcionalidades essenciais |
| RBAC mal definido | Vazamento de dados | Media | Especificar permissoes antes dos CRUDs |
| RLS ausente | Exposicao no Supabase | Media | Criar politicas desde a primeira migration |
| Falta de testes | Regressao | Media | Aplicar TDD por epico |
| Relatorios complexos | Custo de entrega | Media | Comecar com relatorios simples |
