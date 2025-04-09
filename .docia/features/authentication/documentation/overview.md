# Autenticação - Visão Geral

## Introdução

O sistema de autenticação é um componente crítico da aplicação, fornecendo mecanismos seguros para identificação, autenticação e autorização de usuários. Foi implementado usando NextAuth.js/Auth.js integrado com o Next.js 15, oferecendo uma solução robusta e flexível.

## Funcionalidades Principais

O sistema de autenticação oferece:

- **Login e Registro**: Fluxos completos de autenticação de usuários
- **Recuperação de Senha**: Processo seguro para redefinição de senhas
- **Autenticação Social**: Integração com provedores de autenticação terceiros (Google, GitHub)
- **Proteção de Rotas**: Middleware para controle de acesso a páginas protegidas
- **Sessões Seguras**: Gerenciamento de sessões com tokens JWT ou banco de dados
- **RBAC**: Controle de acesso baseado em funções

## Estrutura

```
app/(auth)/
├── login/                # Página de login
│   └── page.tsx
├── register/             # Página de registro
│   └── page.tsx
├── forgot-password/      # Recuperação de senha
│   └── page.tsx
└── reset-password/       # Redefinição de senha
    └── page.tsx

app/api/auth/
└── [...nextauth]/        # Rotas de API para NextAuth.js
    └── route.ts

middleware.ts             # Middleware para proteção de rotas

lib/auth/
├── options.ts            # Configuração do NextAuth.js
├── session.ts            # Utilitários para sessão
└── providers.ts          # Configuração de provedores de autenticação

components/auth/
├── login-form.tsx        # Formulário de login
├── register-form.tsx     # Formulário de registro
├── password-reset-form.tsx # Formulário de redefinição de senha
└── oauth-buttons.tsx     # Botões para autenticação social
```

## Fluxo de Autenticação

### Login com Credenciais

1. Usuário acessa a página de login (`/login`)
2. Preenche o formulário com email e senha
3. Os dados são validados com Zod no cliente
4. Submissão do formulário envia credenciais para a API
5. NextAuth.js verifica as credenciais contra o banco de dados
6. Se válidas, uma sessão é criada e o usuário é redirecionado
7. Se inválidas, mensagens de erro são exibidas no formulário

### Registro de Usuário

1. Usuário acessa a página de registro (`/register`)
2. Preenche o formulário com dados pessoais e credenciais
3. Validação completa dos dados com Zod
4. Submissão cria o usuário no banco de dados
5. Email de verificação é enviado (opcional)
6. Usuário é redirecionado para login ou autenticado automaticamente

### Autenticação Social

1. Usuário clica em um botão de provedor social (Google, GitHub)
2. É redirecionado para o serviço de autenticação do provedor
3. Após autenticação bem-sucedida, retorna à aplicação
4. NextAuth.js cria ou atualiza o usuário no banco de dados
5. Sessão é criada e o usuário é redirecionado

## Middleware de Proteção

O middleware de autenticação:

- Intercepta requisições para rotas protegidas
- Verifica a existência e validade da sessão
- Redireciona para a página de login quando necessário
- Verifica permissões do usuário para acesso a rotas específicas

## Gerenciamento de Sessão

As sessões podem ser configuradas para:

- Armazenamento em JWT (padrão)
- Armazenamento em banco de dados (para revogação)
- Tempo de expiração personalizável
- Renovação automática
- Callback de eventos para ações personalizadas

## Provedores de Autenticação

Provedores suportados:

- **Credenciais**: Email/senha com validação personalizada
- **Google**: Autenticação OAuth com Google
- **GitHub**: Autenticação OAuth com GitHub
- **Outros**: Facilmente extensível para outros provedores OAuth

## Formulários

Os formulários de autenticação utilizam:

- **React Hook Form**: Para gerenciamento de estado e validação
- **Zod**: Para esquemas de validação tipados
- **Shadcn UI**: Para componentes de formulário acessíveis
- **Feedbacks visuais**: Para indicar erros e estados de carregamento

## Segurança

Medidas de segurança implementadas:

- **Hashing de Senhas**: Utilização de bcrypt para armazenamento seguro
- **CSRF Protection**: Proteção contra ataques Cross-Site Request Forgery
- **Rate Limiting**: Limitação de tentativas de login
- **Sanitização de Input**: Prevenção de injeção e XSS
- **HTTPS**: Recomendação de uso para todas as comunicações 