# 📄 Labemanager: Guia de Referência e Execução

![Logo do Labemanager - Visual Branding](https://scontent-for2-1.cdninstagram.com/v/t51.2885-19/467416488_595942433378353_8040070685936133819_n.jpg?stp=dst-jpg_s150x150_tt6&efg=eyJ2ZW5jb2RlX3RhZyI6InByb2ZpbGVfcGljLmRqYW5nby41MDAuYzIifQ&_nc_ht=scontent-for2-1.cdninstagram.com&_nc_cat=101&_nc_oc=Q6cZ2QEgTUq2NEevjt14yuI-jz1-2ZyRkSt7b9B4bDvz10U6vGHL_xPFhb0Caf1ogPNgYfg&_nc_ohc=GkHJKRWKTogQ7kNvwGL3qs9&_nc_gid=xrZ6dQIEBXK4cfc-4QXKmw&edm=AP4sbd4BAAAA&ccb=7-5&oh=00_AfmLMATGYyWktE6mm0X0qqtCRDqhSmgDdIEngepnYHyEJQ&oe=6942B14B&_nc_sid=7a9f4b)

## 1. Visão Geral do Sistema

O Labemanager é um sistema de gerenciamento abrangente, implementado como um **monorepositório**, projetado para centralizar a administração de recursos humanos, financeiros, inventário e eventos. O sistema integra um módulo de frontend para a interface do usuário com um backend robusto para processamento de dados e lógica de negócios.

---

## 2. Arquitetura e Estrutura do Projeto

O repositório está dividido em duas subpastas principais, representando as camadas lógicas da aplicação:

| Diretório | Função | Descrição |
| :--- | :--- | :--- |
| **`labemanager-backend/`** | Servidor e Lógica de Negócios | Contém o servidor, a lógica de aplicação e a camada de acesso a dados (DAL). |
| **`labemanager-frontend/`** | Interface do Usuário (UI) | Contém a aplicação web (client-side) responsável pela renderização e interação do usuário. |

---

## 3. Stack Tecnológico

As tecnologias utilizadas em cada módulo garantem desempenho, escalabilidade e facilidade de manutenção.

### 3.1. Backend (Serviço de API)

| Tecnologia | Versão | Categoria | Função |
| :--- | :--- | :--- | :--- |
| **Node.js** | | Ambiente de Execução | Plataforma para execução do código JavaScript no servidor. |
| **Express.js** | v5 | Framework Web | Criação de rotas e manipulação de requisições HTTP. |
| **SQLite** | | Banco de Dados | Banco de dados relacional leve e baseado em arquivo (`database.sqlite`). |
| **Sequelize** | | ORM | Mapeamento Objeto-Relacional para interagir com o banco de dados. |
| **JWT & Bcrypt** | | Segurança | Gerenciamento de tokens de autenticação (JWT) e criptografia de senhas (Bcrypt). |

### 3.2. Frontend (Interface do Usuário)

| Tecnologia | Versão | Categoria | Função |
| :--- | :--- | :--- | :--- |
| **React** | v19 | Biblioteca UI | Construção da interface de usuário reativa. |
| **Vite** | v7 | Build Tool | Ferramenta de desenvolvimento e empacotamento (`bundling`) de alta performance. |
| **TailwindCSS** | | Framework CSS | Estilização utilitária e responsiva da interface. |
| **React Router** | | Roteamento | Gerenciamento da navegação e rotas na aplicação Single Page Application (SPA). |
| **Axios** | | Cliente HTTP | Comunicação assíncrona com o serviço de API (Backend). |

---

## 4. Procedimento de Execução Local

Siga os passos abaixo para inicializar a aplicação em seu ambiente de desenvolvimento local.

### 4.1. Inicialização do Backend

O servidor de API deve ser iniciado primeiro, pois o frontend depende dele para a comunicação de dados.

1.  Abra o terminal e navegue para o diretório do backend:
    ```bash
    cd labemanager-backend
    ```
2.  Instale as dependências (necessário apenas na primeira execução ou após alterações no `package.json`):
    ```bash
    npm install
    ```
3.  Execute o servidor em modo de desenvolvimento:
    ```bash
    npm run dev
    ```
    > **Observação:** O serviço de API estará acessível na porta `9090`.

### 4.2. Inicialização do Frontend

Após o backend estar ativo, inicie a aplicação cliente (UI).

1.  Abra um **segundo terminal** e navegue para o diretório do frontend:
    ```bash
    cd labemanager-frontend
    ```
2.  Instale as dependências (necessário apenas na primeira execução):
    ```bash
    npm install
    ```
3.  Inicie a aplicação de desenvolvimento:
    ```bash
    npm run dev
    ```
    > A aplicação estará acessível via navegador, tipicamente em `http://localhost:5173`.

---

## 5. Endpoints Principais da API

O serviço de backend expõe as seguintes rotas principais (`Base URL: http://localhost:9090/api`):

| Módulo | Endpoint Base | Função |
| :--- | :--- | :--- |
| **Autenticação** | `/auth` | Gerenciamento de login e registro de usuários. |
| **Finanças** | `/finance/transactions` | CRUD (Criação, Leitura, Atualização, Exclusão) de transações financeiras. |
| **Usuários** | `/pessoas` | Gerenciamento de perfis e dados de usuários (pessoas). |
| **Inventário** | `/almoxarifado` | Controle e consulta de itens em estoque. |
| **Eventos** | `/calendar/events` | Agendamento e listagem de eventos. |

---

## 📝 Suporte

Em caso de problemas na inicialização, verifique as mensagens de erro nos terminais e assegure-se de que todas as dependências foram instaladas corretamente (`npm install`).
