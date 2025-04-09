# Guia de Organização e Estrutura - Next.js 15 Boilerplate

## Visão Geral

Este boilerplate fornece uma estrutura organizada para desenvolver aplicações modernas com Next.js 15, TypeScript, Shadcn UI e Tailwind CSS 4.

## Estrutura Principal

```
.
├── README.md                 # Este arquivo de orientação
├── documentation/            # Documentação completa do projeto
├── app/                      # Diretório principal do Next.js App Router
├── components/               # Componentes React reutilizáveis
├── lib/                      # Bibliotecas e utilitários
├── hooks/                    # React hooks customizados
├── types/                    # Definições de tipos TypeScript
├── config/                   # Configurações da aplicação
├── providers/                # Providers React (Context)
└── public/                   # Ativos públicos estáticos
```

Para uma visão detalhada da estrutura, consulte [documentação/structure.md](documentation/structure.md).

## Instruções de Inicialização

### Requisitos
- Node.js 18.17 ou superior
- npm, yarn ou pnpm

### Instalação
```bash
# Usando npm
npm install

# Usando yarn
yarn

# Usando pnpm
pnpm install
```

### Executando o projeto
```bash
# Desenvolvimento
npm run dev

# Build de produção
npm run build

# Servidor de produção
npm start

# Linting
npm run lint
```

## Comandos Disponíveis

Utilize comandos prefixados com `!` para interagir com o projeto:

- `!read all` - Lê todos os arquivos do projeto dentro da pasta documentation
- `!task list` - Lista todas as tarefas do projeto
- `!show progress` - Mostra o progresso atual do projeto

Consulte [documentation/commands.md](documentation/commands.md) para a lista completa.

## Fluxo de Trabalho para Tarefas

1. Verificar tarefas no backlog
2. Iniciar uma tarefa: `!task start <número>`
3. Atualizar progresso: `!task update <número>`
4. Completar tarefa: `!task complete <número>`

## Documentação de Referência

- [Visão geral da arquitetura](documentation/project/architecture/overview.md)
- [Roadmap do projeto](documentation/project/planning/roadmap.md)
- [Next.js Documentation](https://nextjs.org/docs)
- [Shadcn UI](https://ui.shadcn.com)
- [Tailwind CSS](https://tailwindcss.com/docs)

---

Esta estrutura foi projetada para facilitar o desenvolvimento e a organização de projetos Next.js, permitindo uma compreensão clara do estado atual e dos próximos passos do projeto.