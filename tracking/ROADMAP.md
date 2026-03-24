# Roadmap - Goal Planner

## Visão Geral

**Goal Planner** é uma aplicação pessoal de planejamento estratégico baseada no método "A Única Coisa" de Gary Keller. O aplicativo ajuda usuários a definirem e alcançarem suas metas através de uma estrutura hierárquica rigorosa (G → A → M → S → D), time blocking para produtividade diária, e sistemas de revisão periódica.

**Objetivo Principal:** Criar uma aplicação web completa que permita aos usuários organizar suas vidas em áreas, definir metas hierárquicas, priorizar atividades diárias (ONE Thing), visualizar conexões entre metas (Domino Effect), e acompanhar seu progresso através de dashboards e gamificação.

**Público-Alvo:** Profissionais, estudantes e qualquer pessoa que busca produtividade pessoal através de planejamento estratégico estruturado.

**Stack Tecnológico:**
- Frontend: React 19 + TypeScript + Vite
- Styling: Tailwind CSS + shadcn/ui
- Backend: Supabase (Auth, DB, Storage)
- Database: PostgreSQL
- Hosting: Vercel
- Routing: React Router v7

---

## Milestones

| Milestone | Descrição | Sprint | Entrega Estimada |
|-----------|-----------|--------|------------------|
| M1: Setup | Configuração inicial do projeto, repositório, CI/CD | S1-S2 | Semana 2 |
| M2: Autenticação | Sistema de login/cadastro com Supabase Auth | S3-S4 | Semana 4 |
| M3: Core | Áreas de Vida e Metas Hierárquicas (G→A→M→S→D) | S5-S7 | Semana 7 |
| M4: Execução | Agenda Diária com Time Blocking | S8-S9 | Semana 9 |
| M5: Visualização | Dashboard com progresso visual | S9 | Semana 9 |
| M6: Ampliação | Templates, Revisões Semanal/Mensal | S10-S11 | Semana 11 |
| M7: Engajamento | Sistema de Conquistas (Gamificação) | S12 | Semana 12 |
| M8: Personalização | Configurações, Temas, Notificações | S12 | Semana 12 |
| M9: Qualidade | Testes, Segurança, Otimização | S13-S14 | Semana 14 |
| M10: Launch | Deploy em Produção | S15 | Semana 15 |

---

## Sprint 1: Setup do Projeto

**Objetivo:** Configurar a estrutura base do projeto, incluindo repositório Git, tooling de desenvolvimento, e infraestrutura inicial.

### Tasks

- [ ] Configurar repositório Git com .gitignore e README.md
- [ ] Inicializar projeto Vite com React 19 + TypeScript
- [ ] Configurar ESLint e Prettier para código padronizado
- [ ] Configurar Tailwind CSS com design system (cores, tipografia, radius)
- [ ] Configurar shadcn/ui e instalar componentes base
- [ ] Configurar React Router v7 com estrutura de rotas
- [ ] Configurar Supabase SDK e variáveis de ambiente (.env.example)
- [ ] Configurar script de deploy para Vercel
- [ ] Configurar GitHub Actions para CI/CD básico (lint + build)
- [ ] Criar estrutura de pastas (components, pages, hooks, lib, types)

### Critérios de Aceite

- [ ] Projeto compila sem erros com `npm run build`
- [ ] Servidor de desenvolvimento inicia com `npm run dev`
- [ ] Tailwind CSS configurado com design system definido
- [ ] shadcn/ui instalado e funcionando
- [ ] Rotas básicas configuradas (home, login, dashboard placeholder)
- [ ] Supabase client configurado com Typescript

### Dependências

- Nenhuma (início do projeto)

---

## Sprint 2: Infraestrutura e Database

**Objetivo:** Configurar database PostgreSQL no Supabase, criar schema inicial, e preparar infraestrutura para desenvolvimento.

### Tasks

- [ ] Criar projeto Supabase e configurar PostgreSQL
- [ ] Definir schema do banco (tabelas de usuários, áreas, metas)
- [ ] Criar políticas RLS (Row Level Security) para proteção de dados
- [ ] Configurar storage bucket para imagens/avatares
- [ ] Criar migrations para schema inicial
- [ ] Configurar tipos Typescript para schema do banco
- [ ] Criar seeders para dados de exemplo (templates iniciais)
- [ ] Configurar Supabase Auth com provedores (email/password, Google)
- [ ] Criar script de rollback para migrations
- [ ] Documentar schema do banco (README ou schema.md)

### Critérios de Aceite

- [ ] Todas as tabelas criadas no Supabase
- [ ] Políticas RLS aplicadas e testadas
- [ ] Tipos Typescript gerados e compilando
- [ ] Dados de exemplo inseridos via seed
- [ ] Autenticação via Supabase configurada

### Dependências

- [ ] Sprint 1 concluída

---

## Sprint 3: Autenticação - Frontend

**Objetivo:** Implementar interface de autenticação (login, registro, recuperação de senha) com Supabase Auth.

### Tasks

- [ ] Criar página de Login com design system
- [ ] Criar página de Registro com validação de campos
- [ ] Criar página de Recuperação de Senha
- [ ] Implementar integração com Supabase Auth (hooks customizados)
- [ ] Criar componente de Toast para notificações de auth
- [ ] Implementar proteção de rotas (Private Routes)
- [ ] Criar contexto de Auth para gerenciamento de estado
- [ ] Implementar logout com redirect para login
- [ ] Adicionar validação de formulários (Zod + React Hook Form)
- [ ] Criar página de perfil do usuário (após login)

### Critérios de Aceite

- [ ] Usuário consegue criar conta
- [ ] Usuário consegue fazer login
- [ ] Usuário consegue recuperar senha
- [ ] Rota protegida redireciona para login se não autenticado
- [ ] State de autenticação persiste entre reloads
- [ ] Design responsivo e acessível

### Dependências

- [ ] Sprint 1 concluída
- [ ] Sprint 2 (schema de usuários)

---

## Sprint 4: Autenticação - Backend & Core Setup

**Objetivo:** Finalizar configuração de autenticação no backend e preparar estrutura base para módulos principais.

### Tasks

- [ ] Configurar triggers no Supabase para criação de perfil
- [ ] Implementar validação de email no backend
- [ ] Criar funções Edge para operações de autenticação
- [ ] Configurar webhooks para eventos de auth
- [ ] Implementar session management (refresh tokens)
- [ ] Criar componente de Loading/Skeleton para transições
- [ ] Implementar redirect após login bem-sucedido
- [ ] Criar estrutura de Layout base (Header, Sidebar, Main Content)
- [ ] Implementar Menu Mobile Inferior com 5 módulos
- [ ] Criar tema escuro (Dark Mode) base

### Critérios de Aceite

- [ ] Perfil criado automaticamente após registro
- [ ] Sessão persiste adequadamente
- [ ] Layout responsivo (desktop e mobile)
- [ ] Menu inferior funcional em mobile
- [ ] Dark Mode toggle funcionando
- [ ] Redirects funcionando corretamente

### Dependências

- [ ] Sprint 3 concluída

---

## Sprint 5: Áreas de Vida - CRUD Completo

**Objetivo:** Implementar módulo de Áreas de Vida com CRUD completo, incluindo criação, edição, listagem e exclusão.

### Tasks

- [ ] Criar página de listagem de Áreas de Vida
- [ ] Criar componente de Card para cada Área
- [ ] Implementar modal de criação de nova Área
- [ ] Implementar modal de edição de Área
- [ ] Implementar exclusão de Área com confirmação
- [ ] Criar página de detalhes de uma Área
- [ ] Implementar ordenação/priorização de Áreas (drag & drop)
- [ ] Adicionar cor personalizada para cada Área
- [ ] Implementar ícones para Áreas (selection grid)
- [ ] Criar estado vazio (empty state) para quando não há áreas

### Critérios de Aceite

- [ ] Usuário consegue criar uma nova Área
- [ ] Usuário consegue editar uma Área existente
- [ ] Usuário consegue excluir uma Área
- [ ] Áreas aparecem em ordem de prioridade
- [ ] Cada Área tem cor e ícone distintos
- [ ] Interface responsiva e fluida

### Dependências

- [ ] Sprint 4 concluída
- [ ] Schema de Áreas no banco (Sprint 2)

---

## Sprint 6: Metas Hierárquicas - Estrutura G→A→M→S→D

**Objetivo:** Implementar a hierarquia completa de metas: Grand Goal → Annual → Monthly → Weekly → Daily.

### Tasks

- [ ] Criar schema de Metas no banco (com self-referencing)
- [ ] Criar página de listagem de Metas por nível
- [ ] Implementar criação de Grand Goal (nível 1)
- [ ] Implementar criação de Metas Anuais (nível 2) vinculadas a GG
- [ ] Implementar criação de Metas Mensais (nível 3) vinculadas a A
- [ ] Implementar criação de Metas Semanais (nível 4) vinculadas a M
- [ ] Implementar criação de Tarefas Diárias (nível 5) vinculadas a S
- [ ] Criar visualização de hierarquia em árvore (tree view)
- [ ] Implementar navegação entre níveis de meta
- [ ] Criar breadcrumbs para navegação hierárquica

### Critérios de Aceite

- [ ] Hierarquia completa visível e navegável
- [ ] Cada meta mostra suas sub-metas
- [ ] Navegação entre níveis funciona corretamente
- [ ] Breadcrumbs mostram caminho completo
- [ ] Criação de meta em qualquer nível funciona

### Dependências

- [ ] Sprint 5 concluída
- [ ] Schema de Metas (Sprint 2)

---

## Sprint 7: Metas - Features Avançadas

**Objetivo:** Adicionar recursos avançados às metas: ONE Thing, SMART, prazo, progresso, e conexões.

### Tasks

- [ ] Implementar seleção de ONE Thing por nível hierárquico
- [ ] Adicionar campos SMART às metas (Smart, Measurable, Achievable, Relevant, Time-bound)
- [ ] Implementar sistema de progresso automático (% completada)
- [ ] Adicionar campo de prazo (due date) com validação
- [ ] Implementar sistema de Domino Effect (metas conectadas)
- [ ] Criar visualização de dependências entre metas
- [ ] Implementar marcação de meta como concluída
- [ ] Adicionar notas/descrição rica às metas (markdown)
- [ ] Implementar busca e filtro de metas
- [ ] Criar atalhos de teclado para navegação

### Critérios de Aceite

- [ ] ONE Thing claramente visível em cada nível
- [ ] Campos SMART editáveis e salvos
- [ ] Progresso calculado corretamente
- [ ] Conexões entre metas visíveis (Domino Effect)
- [ ] Busca e filtros funcionando

### Dependências

- [ ] Sprint 6 concluída

---

## Sprint 8: Agenda Diária - Time Blocking

**Objetivo:** Implementar sistema de agenda com time blocking (manhã/tarde/noite) vinculado às tarefas diárias.

### Tasks

- [ ] Criar schema de Time Blocks no banco
- [ ] Criar página de Agenda Diária
- [ ] Implementar visualização de manhã (6h-12h)
- [ ] Implementar visualização de tarde (12h-18h)
- [ ] Implementar visualização de noite (18h-22h)
- [ ] Criar modal de criação de Time Block
- [ ] Implementar arrastar e soltar para agendar tarefas
- [ ] Criar listagem de tarefas disponíveis para agendar
- [ ] Implementar edição e exclusão de Time Blocks
- [ ] Adicionar indicador de prioridade visual nos blocks

### Critérios de Aceite

- [ ] Agenda mostra os três períodos do dia
- [ ] Usuário consegue criar Time Block
- [ ] Usuário consegue agendar tarefa em um bloco
- [ ] Arrastar e soltar funciona corretamente
- [ ] Visualização responsiva

### Dependências

- [ ] Sprint 7 concluída
- [ ] Schema de Time Blocks (Sprint 2)

---

## Sprint 9: Dashboard e Visualização de Progresso

**Objetivo:** Criar dashboard principal com visualização de progresso, estatísticas e overview das atividades.

### Tasks

- [ ] Criar schema de métricas no banco
- [ ] Criar componente de widget de progresso geral
- [ ] Implementar gráfico de progresso por Área de Vida
- [ ] Implementar widget de ONE Thing do dia atual
- [ ] Criar widget de Time Blocks agendados hoje
- [ ] Implementar widget de metas próximas (próxima semana)
- [ ] Criar widget de conquistas recentes
- [ ] Adicionar atalhos rápidos (quick actions)
- [ ] Implementar filtros de período (dia, semana, mês)
- [ ] Criar animação de transição no dashboard

### Critérios de Aceite

- [ ] Dashboard mostra visão geral completa
- [ ] Progresso de cada Área visível
- [ ] ONE Thing do dia claramente destacado
- [ ] Time Blocks do dia visíveis
- [ ] Métricas atualizadas em tempo real

### Dependências

- [ ] Sprint 8 concluída

---

## Sprint 10: Templates de Metas

**Objetivo:** Implementar sistema de templates para facilitar criação de metas com estruturas pré-definidas.

### Tasks

- [ ] Criar schema de Templates no banco
- [ ] Criar biblioteca de templates pré-definidos
- [ ] Implementar página de listagem de templates
- [ ] Criar modal de visualização de template
- [ ] Implementar aplicação de template a uma Área
- [ ] Implementar criação de template personalizado
- [ ] Criar categorias de templates (carreira, saúde, finanças, etc.)
- [ ] Implementar busca de templates
- [ ] Adicionar preview da estrutura do template
- [ ] Criar opção de "usar novamente" em metas concluídas

### Critérios de Aceite

- [ ] Templates pré-definidos disponíveis
- [ ] Usuário consegue criar meta a partir de template
- [ ] Usuário consegue criar template personalizado
- [ ] Categorização funcionando

### Dependências

- [ ] Sprint 7 concluída
- [ ] Schema de Templates (Sprint 2)

---

## Sprint 11: Revisões Semanal e Mensal

**Objetivo:** Implementar sistema de revisões periódicas para planejamento e reflexão.

### Tasks

- [ ] Criar schema de Revisões no banco
- [ ] Criar página de Revisão Semanal
- - Implementar checklist de avaliação da semana
- [ ] Criar template de perguntas para reflexão semanal
- [ ] Implementar revisão de metas da semana (concluídas/pendentes)
- [ ] Implementar planejamento da próxima semana
- [ ] Criar página de Revisão Mensal
- [ ] Criar template de perguntas para reflexão mensal
- [ ] Implementar revisão de metas do mês
- [ ] Implementar análise de progresso por Área
- [ ] Criar geração automática de insights

### Critérios de Aceite

- [ ] Revisão Semanal funcional e completa
- [ ] Revisão Mensal funcional e completa
- [ ] Dados de referência preenchidos automaticamente
- [ ] Histórico de revisões preservado
- [ ] Insights gerados corretamente

### Dependências

- [ ] Sprint 9 concluída

---

## Sprint 12: Conquistas e Configurações

**Objetivo:** Implementar sistema de gamificação (conquistas) e configurações personalizadas.

### Tasks

**Conquistas:**
- [ ] Definir achievement types no banco
- [ ] Implementar sistema de pontos/XP
- [ ] Criar lógica de desbloqueio de conquistas
- [ ] Criar página de Galeria de Conquistas
- [ ] Implementar badges por categoria (streak, completion, etc.)
- [ ] Adicionar notificação de conquista desbloqueada
- [ ] Criar ranking pessoal (progress over time)

**Configurações:**
- [ ] Criar página de Configurações
- [ ] Implementar edição de perfil (nome, avatar, bio)
- [ ] Implementar seleção de tema (cores customizáveis)
- [ ] Implementar Dark Mode toggle global
- [ ] Configurar preferências de notificação
- [ ] Implementar exportação de dados (JSON)
- [ ] Criar página de preferências de idioma
- [ ] Implementar delete de conta

### Critérios deacrylate

- [ ] Sistema de conquistas funcionando
- [ ] Conquistas desbloqueiam corretamente
- [ ] Galeria de conquistas visível
- [ ] Configurações de perfil funcionando
- [ ] Temas customizáveis funcionando
- [ ] Dark Mode persistindo

### Dependências

- [ ] Sprint 11 concluída

---

## Sprint 13: Testes e Qualidade

**Objetivo:** Garantir qualidade do código através de testes unitários, integração e E2E.

### Tasks

- [ ] Configurar Jest/Vitest para testes unitários
- [ ] Criar testes unitários para hooks customizados
- [ ] Criar testes unitários para utilitários (utils)
- [ ] Criar testes para componentes principais (Button, Card, Input)
- [ ] Configurar testes de integração com React Testing Library
- [ ] Criar testes de integração para fluxo de autenticação
- [ ] Criar testes de integração para CRUD de Áreas
- [ ] Configurar testes E2E com Playwright
- [ ] Criar teste E2E para jornada do usuário (criar meta até completar)
- [ ] Configurar coverage report (target: 70%)

### Critérios de Aceite

- [ ] Testes unitários passando (>50% coverage)
- [ ] Testes de integração cobrindo fluxos principais
- [ ] Testes E2E passando em ambiente limpo
- [ ] CI/CD executando testes automaticamente

### Dependências

- [ ] Sprint 12 concluída
- [ ] Feature flags configurados se necessário

---

## Sprint 14: Segurança e Otimização

**Objetivo:** Fortalecer segurança da aplicação e otimizar performance.

### Tasks

**Segurança:**
- [ ] Auditar e corrigir vulnerabilidades (npm audit)
- [ ] Implementar headers de segurança (CSP, X-Frame-Options)
- [ ] Adicionar proteção CSRF
- [ ] Implementar rate limiting em API calls
- [ ] Revisar e fortalecer políticas RLS do Supabase
- [ ] Adicionar sanitização de inputs
- [ ] Implementar logging de segurança
- [ ] Realizar penetration test básico

**Otimização:**
- [ ] Analisar bundle size e otimizar (code splitting)
- [ ] Implementar lazy loading de rotas
- [ ] Otimizar imagens (next/image ou similar)
- [ ] Implementar cache de dados (React Query)
- [ ] Adicionar prefetching de dados
- [ ] Monitorar Core Web Vitals
- [ ] Implementar critical CSS inline

### Critérios de Aceite

- [ ] Nenhuma vulnerabilidade crítica encontrada
- [ ] Headers de segurança aplicados
- [ ] Bundle size < 200KB (gzipped)
- [ ] LCP < 2.5s, FID < 100ms, CLS < 0.1

### Dependências

- [ ] Sprint 13 concluída

---

## Sprint 15: Launch e Deploy

**Objetivo:** Preparar e executar deploy em produção, configurações finais de monitoramento.

### Tasks

- [ ] Configurar ambiente de produção no Supabase
- [ ] Configurar variáveis de ambiente de produção
- [ ] Executar deploy para Vercel (production)
- [ ] Configurar domínio personalizado (se aplicável)
- [ ] Configurar SSL/HTTPS
- [ ] Configurar monitoramento (Sentry, Analytics)
- [ ] Configurar alertas de erro
- [ ] Criar documentação de uso (guia do usuário)
- [ ] Criar documentação técnica (README.md)
- [ ] Executar teste de carga básico
- [ ] Executar smoke tests em produção
- [ ] Preparar comunicação de launch (release notes)

### Critérios de Aceite

- [ ] Aplicação online e acessível em produção
- [ ] Domínio funcionando com HTTPS
- [ ] Monitoramento configurado e ativo
- [ ] Documentação completa
- [ ] Smoke tests passando

### Dependências

- [ ] Sprint 14 concluída
- [ ] Todos os testes passando

---

## Resumo de Sprints

| Sprint | Nome | Focus Principal | Duração Estimada |
|--------|------|-----------------|------------------|
| S1 | Setup do Projeto | Infraestrutura inicial | 1 semana |
| S2 | Infraestrutura e Database | Database e Supabase | 1 semana |
| S3 | Autenticação - Frontend | UI de auth | 1 semana |
| S4 | Autenticação - Backend & Core | Auth + Layout base | 1 semana |
| S5 | Áreas de Vida - CRUD | Módulo 1 completo | 1 semana |
| S6 | Metas Hierárquicas | Estrutura G→A→M→S→D | 1 semana |
| S7 | Metas - Features Avançadas | ONE Thing, SMART, Domino | 1 semana |
| S8 | Agenda Diária - Time Blocking | Módulo 3 completo | 1 semana |
| S9 | Dashboard | Visualização de progresso | 1 semana |
| S10 | Templates | Biblioteca de templates | 1 semana |
| S11 | Revisões | Semanal e Mensal | 1 semana |
| S12 | Conquistas e Configurações | Gamificação + Settings | 1 semana |
| S13 | Testes | Unit, Integração, E2E | 1 semana |
| S14 | Segurança e Otimização | Performance e hardening | 1 semana |
| S15 | Launch | Deploy final | 1 semana |

**Total Estimado:** 15 semanas

---

## Notas Adicionais

- **Feedback Contínuo:** Ao final de cada sprint, revisar progresso com stakeholders e ajustar roadmap se necessário.
- **Feature Flags:** Para funcionalidades de risco, usar feature flags e ativar gradualmente.
- **Rollback:** Manter capacidade de rollback para cada deploy.
- **Monitoramento:** Métricas de uso e performance devem ser monitoradas continuamente após launch.
- **Technical Debt:** Reservar 20% do tempo de cada sprint para dívida técnica e refatoração.