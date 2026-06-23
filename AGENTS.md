# AGENTS.md - Regras para Agentes no Repositorio

**Projeto:** Tyr_Controle  
**Atualizado em:** 2026-06-23  
**Idioma:** pt-BR  

---

## 1. Objetivo

Este arquivo define como agentes de IA, automacoes e colaboradores tecnicos devem atuar no repositorio Tyr_Controle.

As regras abaixo orientam investigacao antes de mudancas, uso de Specification-Driven Development (SDD), Test-Driven Development (TDD), padrao de commits, seguranca, rastreabilidade e atualizacao obrigatoria da documentacao do projeto.

## 2. Principios obrigatorios

- Sempre buscar contexto antes de alterar arquivos.
- Sempre trabalhar com mudancas pequenas, rastreaveis e revisaveis.
- Sempre atualizar documentacao junto com codigo.
- Nunca inventar comportamento, endpoints, schemas, regras de negocio ou status de implementacao.
- Quando algo nao estiver confirmado, registrar como `A CONFIRMAR`, `PENDENTE DE VALIDACAO` ou `NAO IDENTIFICADO NO REPOSITORIO`.
- Nunca mascarar erro com mock, stub ou fallback falso sem documentacao.
- Nunca expor secrets, tokens, senhas, chaves privadas ou credenciais.
- Nunca fazer commit ou push sem autorizacao explicita do usuario.
- Nunca deixar o projeto em estado quebrado.
- Sempre registrar decisoes relevantes em `CONTEXTO.md`.

## 3. Stack oficial do projeto

- Frontend: Next.js App Router, React e TypeScript.
- Backend: Server Actions e Route Handlers do Next.js.
- Banco de dados: PostgreSQL via Supabase.
- Autenticacao: Supabase Auth.
- Autorizacao: RBAC por perfis.
- ORM: Prisma.
- Validacao: Zod.
- UI: Tailwind CSS, shadcn/ui e lucide-react.
- Formularios: React Hook Form com Zod.
- Tabelas: TanStack Table.
- Graficos: Recharts.
- Datas: date-fns.
- Testes unitarios/integrados: Vitest e React Testing Library.
- Testes E2E: Playwright.
- Deploy: Vercel.
- Storage: Supabase Storage.

## 4. Regras de commit em pt-BR

Todo commit deve seguir Conventional Commits em portugues do Brasil.

Tipos permitidos:

- `feat:` nova funcionalidade
- `fix:` correcao de bug
- `docs:` documentacao
- `test:` testes
- `refactor:` refatoracao sem mudanca funcional
- `style:` formatacao sem mudanca logica
- `chore:` tarefas auxiliares
- `ci:` pipeline, deploy e integracao continua
- `perf:` melhoria de performance
- `build:` build, dependencias ou empacotamento
- `revert:` reversao de alteracao anterior

Formato:

```text
<tipo>(<escopo>): <descricao curta em pt-BR>

<corpo opcional explicando motivo, impacto e arquivos principais>
```

Exemplos:

```text
feat(auth): adiciona autenticacao com Supabase
fix(api): corrige validacao de payload no cadastro de projeto
docs(arquitetura): registra stack oficial do sistema
test(tarefas): adiciona testes para atualizacao de status
```

Regras adicionais:

- Um commit por tarefa concluida.
- Nao misturar mudancas nao relacionadas.
- Escopos sugeridos: `auth`, `frontend`, `backend`, `banco`, `docs`, `infra`, `tests`, `dashboard`, `projetos`, `tarefas`.
- Validar testes, build e documentacao antes de commit.
- Commit e push somente com autorizacao explicita.

## 5. SDD - Specification-Driven Development

Toda funcionalidade deve comecar por especificacao.

Antes de codificar, o agente deve:

1. Ler `CONTEXTO.md`, `ESCOPO.md`, `ROADMAP.md`, `ARQUITETURA.md` e `BANCO_DADOS.md`.
2. Confirmar o requisito e seu impacto.
3. Criar ou atualizar a especificacao.
4. Definir criterios de aceite.
5. Mapear impacto em arquitetura, banco, API, frontend, testes, infraestrutura e seguranca.
6. Registrar decisoes relevantes em `CONTEXTO.md`.
7. Atualizar `ROADMAP.md` quando a tarefa fizer parte de fase, epico ou historia.

Toda especificacao deve conter:

- Objetivo
- Contexto
- Regras de negocio
- Fluxo esperado
- Criterios de aceite
- Impacto tecnico
- Testes necessarios
- Riscos
- Dependencias

## 6. TDD - Test-Driven Development

Fluxo obrigatorio:

1. RED: escrever ou ajustar teste que falha.
2. GREEN: implementar o minimo necessario para passar.
3. REFACTOR: melhorar mantendo testes verdes.

Regras:

- Toda feature nova precisa de teste.
- Todo bug corrigido precisa de teste de regressao.
- Toda regra de negocio critica precisa de teste.
- Toda migration relevante precisa ser validada.
- Nao reduzir cobertura sem justificativa em `RELATORIO.md`.
- Se testes ainda nao estiverem configurados, registrar a pendencia no roadmap.

Comandos esperados para a stack oficial:

```bash
npm install
npm run dev
npm run lint
npm run test
npm run test:e2e
npm run build
npx prisma migrate dev
npx prisma studio
```

## 7. Atualizacao obrigatoria de documentacao

Arquivos que devem ser atualizados conforme impacto:

- `ARQUITETURA.md`: mudancas estruturais, modulos, fluxos, integrações ou stack.
- `BANCO_DADOS.md`: tabelas, models, migrations, indices, constraints ou seeds.
- `ESCOPO.md`: requisitos, regras de negocio ou limites do projeto.
- `ROADMAP.md`: fases, epicos, prioridades, historias ou tarefas.
- `CONTEXTO.md`: decisoes tecnicas, bloqueios, mudancas relevantes e estado atual.
- `RELATORIO.md`: registro ao final de cada sessao relevante.

Checklist por tarefa:

```markdown
- [ ] Requisito compreendido
- [ ] Especificacao criada/atualizada
- [ ] Teste criado/atualizado
- [ ] Implementacao validada
- [ ] Documentacao atualizada
- [ ] Arquitetura atualizada, se aplicavel
- [ ] Banco de dados atualizado, se aplicavel
- [ ] Roadmap atualizado, se aplicavel
- [ ] Contexto atualizado
- [ ] Relatorio atualizado
```

## 8. Seguranca e integridade

- Nunca expor `.env`, tokens, senhas, chaves privadas ou credenciais.
- Nunca copiar secrets para documentacao.
- Usar exemplos ficticios seguros.
- Nunca usar `service_role` do Supabase em codigo client-side.
- Habilitar RLS por padrao em tabelas expostas do Supabase.
- Nao usar `user_metadata` como fonte de autorizacao; usar `app_metadata` ou tabelas de perfil controladas pelo backend.
- Validar entradas com Zod.
- Documentar riscos de seguranca encontrados em `CONTEXTO.md`.

## 9. Conduta para agentes

- Ser conservador em mudancas.
- Priorizar consistencia com padroes existentes.
- Nao reescrever o projeto sem necessidade.
- Nao substituir bibliotecas principais sem justificativa.
- Nao remover testes.
- Nao apagar historico de documentacao.
- Em caso de duvida, investigar antes de perguntar.
- Se ainda houver duvida, registrar como `A CONFIRMAR`.
