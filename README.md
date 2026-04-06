# Volpe - Plataforma Educacional de Programacao

Volpe e uma plataforma web educacional desenvolvida como Trabalho de Conclusao de Curso (TCC), voltada para o ensino de linguagens de programacao. O sistema oferece um ambiente colaborativo de aprendizado para estudantes da ETEC (Escola Tecnica Estadual de Sao Paulo).

## Sobre o Projeto

A plataforma Volpe foi criada para facilitar o aprendizado de programacao atraves de materiais organizados por disciplina, forum de duvidas, chat em tempo real, quizzes interativos e compartilhamento de arquivos.

## Funcionalidades

### Autenticacao
- Cadastro de usuarios com validacao de email institucional (@etec.sp.gov.br)
- Login/logout com sessoes seguras
- Senhas criptografadas com bcrypt

### Disciplinas (Materias)
- Catalogo de disciplinas de programacao (HTML, CSS, JavaScript, PHP)
- Cada disciplina possui banner, descricao e recursos associados
- Canal de chat dedicado por disciplina

### Forum
- Publicacao de duvidas com tags de linguagem de programacao
- Sistema de respostas com likes/dislikes
- Edicao e exclusao de perguntas e respostas
- Navegacao por disciplina

### Chat por Disciplina
- Mensagens em canais especificos por materia
- Edicao e exclusao de mensagens
- Compartilhamento de arquivos e recursos

### Quizzes e Atividades
- Atividades organizadas por linguagem de programacao
- Questoes de quiz dentro de cada atividade
- Acompanhamento de progresso

### Perfil de Usuario
- Visualizacao de perfil com atividades do usuario
- Upload e atualizacao de foto de perfil
- Historico de respostas curtidas e arquivos salvos

### Busca
- Sistema de busca em toda a plataforma

## Tecnologias Utilizadas

### Backend
- **PHP 8.1+**
- **Laravel 10.0**
- **MySQL** (porta 3308)
- **Laravel Sanctum** (autenticacao de API)

### Frontend
- **Blade** (template engine do Laravel)
- **Vite 4.0** (bundler de assets)
- **Axios 1.1.2** (requisicoes HTTP)
- **CSS** customizado
- **JavaScript**

## Estrutura do Projeto

```
TCC/
├── app/
│   ├── Http/Controllers/     # Controladores (Auth, Chat, Forum, Quiz, etc.)
│   └── Models/               # Modelos Eloquent (User, Subject, ForumPost, etc.)
├── routes/
│   ├── web.php               # Rotas web (30+)
│   └── api.php               # Rotas API com Sanctum
├── resources/
│   ├── views/                # Templates Blade
│   │   ├── forum/            # Paginas do forum
│   │   ├── subjects/         # Paginas das disciplinas/chat
│   │   ├── atividades/       # Paginas de atividades
│   │   └── layouts/          # Layouts base
│   ├── css/                  # Estilos customizados
│   └── js/                   # JavaScript frontend
├── database/
│   └── migrations/           # 14 migrations
└── public/
    └── images/               # Banners e assets
```

## Pre-requisitos

- PHP >= 8.1
- Composer
- Node.js e npm
- MySQL

## Instalacao

1. Clone o repositorio:
```bash
git clone https://github.com/maxx0501/TCC.git
cd TCC
```

2. Instale as dependencias PHP:
```bash
composer install
```

3. Instale as dependencias JavaScript:
```bash
npm install
```

4. Configure o ambiente:
```bash
cp .env.example .env
php artisan key:generate
```

5. Configure o banco de dados no arquivo `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3308
DB_DATABASE=volpe
DB_USERNAME=root
DB_PASSWORD=
```

6. Execute as migrations:
```bash
php artisan migrate
```

7. Inicie o servidor de desenvolvimento:
```bash
php artisan serve
npm run dev
```

8. Acesse a aplicacao em `http://localhost:8000`

## Banco de Dados

O sistema utiliza as seguintes tabelas principais:
- **users** - Usuarios da plataforma
- **subjects** - Disciplinas/materias
- **chat_posts** - Mensagens nos chats das disciplinas
- **forum_posts** - Perguntas do forum
- **forum_answers** - Respostas do forum
- **likes** - Sistema de curtidas
- **quiz_activities** - Atividades de quiz
- **quiz_questions** - Questoes dos quizzes
- **files** - Arquivos das disciplinas
- **saved_files** - Arquivos salvos pelos usuarios

## Autores

Desenvolvido como Trabalho de Conclusao de Curso (TCC) por estudantes da ETEC.

## Licenca

Este projeto esta licenciado sob a [MIT License](https://opensource.org/licenses/MIT).
