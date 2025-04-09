# Estrutura de Pastas do Projeto Next.js

Este documento descreve a estrutura de pastas recomendada para projetos Next.js 15 que utilizam este template. A estrutura foi projetada para facilitar a organização de documentação, tarefas e features do projeto.

## Visão Geral

```
.
├── README.md                     # Visão geral do projeto e instruções iniciais
├── .docia/                       # Documentação do projeto
│   ├── commands.md               # Lista de comandos disponíveis para interação
│   ├── state.md                  # Estado atual do projeto e progresso
│   ├── structure.md              # Este arquivo (estrutura de pastas)
│   ├── features/                 # Pasta para features do sistema
│   │   └── [feature-name]/       # Um diretório para cada feature
│   │       ├── documentation/    # Documentação da feature
│   │       │   └── overview.md   # Visão geral da feature
│   │       ├── backlog/          # Tarefas planejadas para o futuro
│   │       │   └── [number]-[name]/  # Pasta para cada tarefa no backlog
│   │       │       └── [number]-[name].md       # Descrição da tarefa
│   │       ├── in-progress/      # Tarefas em andamento
│   │       │   └── [number]-[name]/  # Pasta para cada tarefa em andamento
│   │       │       ├── [number]-[name].md       # Descrição da tarefa
│   │       │       └── [number]-[name].result.md     # Resultados parciais da tarefa
│   │       └── completed/        # Tarefas concluídas
│   │           └── [number]-[name]/  # Pasta para cada tarefa concluída
│   │               ├── [number]-[name].md       # Descrição da tarefa
│   │               └── [number]-[name].result.md     # Resultados da tarefa
│   └── project/                  # Documentação geral do projeto
│       ├── documentation/        # Documentação principal
│       │   └── context.md        # Contexto geral do projeto
│       ├── planning/             # Planejamento do projeto
│       │   └── roadmap.md        # Roadmap e cronograma
│       ├── architecture/         # Documentação de arquitetura
│       │   └── overview.md       # Visão geral da arquitetura
│       └── analysis/             # Análises e estudos
│           └── [analysis-name].md    # Documentos de análise específicos
├── app/                          # Diretório principal do Next.js App Router
│   ├── (auth)/                   # Grupo de rotas de autenticação
│   │   ├── login/                # Rota de login
│   │   │   └── page.tsx          # Página de login
│   │   └── register/             # Rota de registro
│   │       └── page.tsx          # Página de registro
│   ├── (dashboard)/              # Grupo de rotas do dashboard
│   │   ├── layout.tsx            # Layout compartilhado do dashboard
│   │   └── page.tsx              # Página principal do dashboard
│   ├── api/                      # Rotas de API do Next.js
│   │   └── [endpoints]/          # Endpoints da API
│   │       └── route.ts          # Handlers dos endpoints
│   ├── globals.css               # Estilos globais
│   ├── layout.tsx                # Layout principal da aplicação
│   └── page.tsx                  # Página inicial do site
├── components/                   # Componentes React reutilizáveis
│   ├── ui/                       # Componentes de UI do Shadcn
│   │   ├── button.tsx            # Componente de botão
│   │   ├── input.tsx             # Componente de input
│   │   └── [outros-componentes].tsx
│   ├── forms/                    # Componentes de formulários
│   │   └── [form-components].tsx
│   └── [feature-components]/     # Componentes específicos de features
│       └── [component].tsx
├── lib/                          # Bibliotecas e utilitários
│   ├── utils.ts                  # Funções utilitárias
│   └── [feature]/                # Lógica específica de features
│       └── [utility].ts
├── hooks/                        # React hooks customizados
│   └── use-[hook-name].ts
├── types/                        # Definições de tipos TypeScript
│   ├── index.d.ts                # Tipos globais
│   └── [feature]/                # Tipos específicos por feature
├── config/                       # Configurações da aplicação
│   └── [config-files].ts
├── providers/                    # Providers React (Context)
│   └── [provider].tsx
├── styles/                       # Estilos complementares
│   └── [style-files].css
├── public/                       # Ativos públicos estáticos
│   ├── images/
│   ├── fonts/
│   └── favicon.ico
├── middleware.ts                 # Middleware do Next.js
├── next.config.js                # Configuração do Next.js
├── tailwind.config.js            # Configuração do Tailwind CSS
├── components.json               # Configuração do Shadcn
├── tsconfig.json                 # Configuração do TypeScript
└── package.json                  # Dependências e scripts
```

## Detalhamento das Pastas

### Documentação

- **documentation/**: Contém toda a documentação do projeto, com a mesma estrutura descrita anteriormente.

### App Router Next.js 15

- **app/**: O diretório principal do App Router do Next.js.
  - **layout.tsx**: Layout raiz da aplicação, incluindo providers globais.
  - **page.tsx**: Página inicial da aplicação.
  - **globals.css**: Estilos globais incluindo as configurações do Tailwind CSS.
  - **api/**: Rotas da API.
  - **Grupos de rotas**: Organizados em pastas com parênteses (por exemplo, `(dashboard)`) para agrupamento lógico.

### Componentes

- **components/**: Componentes React reutilizáveis.
  - **ui/**: Componentes UI do Shadcn.
  - **forms/**: Componentes relacionados a formulários.
  - **[feature-components]/**: Componentes específicos para cada feature.

### Bibliotecas e Utilitários

- **lib/**: Bibliotecas e funções utilitárias.
- **hooks/**: React hooks customizados.
- **types/**: Definições de tipos TypeScript.
- **config/**: Arquivos de configuração.
- **providers/**: Providers de contexto React.

### Arquivos de Configuração

- **next.config.js**: Configuração do Next.js.
- **tailwind.config.js**: Configuração do Tailwind CSS 4.
- **components.json**: Configuração do Shadcn.
- **tsconfig.json**: Configuração do TypeScript.
- **package.json**: Dependências e scripts.

## Convenções de Nomenclatura

1. **Componentes React**: Use PascalCase (ex: `Button.tsx`).
2. **Hooks**: Prefixados com `use` e em camelCase (ex: `useAuthState.ts`).
3. **Páginas e Rotas**: Use kebab-case para diretórios de rotas (ex: `user-profile/`).
4. **Arquivos TypeScript**: Use camelCase (ex: `authUtils.ts`).
5. **Tarefas**: Mesmo formato anterior `[number]-[task-name]`.

## Gerenciamento de Tarefas

As tarefas seguem o mesmo fluxo de trabalho descrito anteriormente, utilizando os comandos definidos em `commands.md`. 