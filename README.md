<div align="center">

# 🍔 DevBurguer — API

> API RESTful para gerenciamento completo de uma hamburgueria: produtos, categorias, usuários e pedidos.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

[🔗 Ver Front-end](https://github.com/Joseph24augusto27/devburguer-front) &nbsp;|&nbsp; [📄 Rotas da API](#-rotas-da-api)

</div>

---

## 📋 Sobre o Projeto

A **DevBurguer API** é o back-end de uma aplicação completa de hamburgueria, desenvolvida durante o curso da **DevClub**. Responsável por toda a lógica de negócio: autenticação de usuários, gerenciamento de produtos e categorias, e controle de pedidos.

> 💡 Este projeto faz parte de uma aplicação Full Stack. Veja também o [repositório do front-end](https://github.com/Joseph24augusto27/devburguer-front).

---

## ✨ Funcionalidades

- 🔐 Autenticação com JWT (JSON Web Token)
- 👤 CRUD de usuários (cadastro, login, perfil)
- 🍔 CRUD de produtos com upload de imagem
- 🗂️ Gerenciamento de categorias
- 📦 Criação e atualização de pedidos
- 🔒 Rotas protegidas para administradores

---

## 🚀 Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| **Node.js** | Runtime do servidor |
| **Express** | Framework web |
| **PostgreSQL** | Banco de dados relacional |
| **Sequelize** | ORM para comunicação com o banco |
| **JWT** | Autenticação e autorização |
| **Bcrypt** | Hash de senhas |
| **Multer** | Upload de imagens |
| **Yup** | Validação de dados |

---

## 🖥️ Como Rodar o Projeto Localmente

### Pré-requisitos

- [Node.js](https://nodejs.org/) v16 ou superior
- [PostgreSQL](https://www.postgresql.org/) instalado e rodando

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/Joseph24augusto27/devburguer-back.git

# Entre na pasta do projeto
cd devburguer-back

# Instale as dependências
npm install

# Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com suas credenciais do banco
```

Exemplo de `.env`:
```env
PORT=3001
DB_HOST=localhost
DB_USER=seu_usuario
DB_PASS=sua_senha
DB_NAME=devburguer
JWT_SECRET=sua_chave_secreta
```

```bash
# Rode as migrations para criar as tabelas
npx sequelize db:migrate

# (Opcional) Popule o banco com dados iniciais
npx sequelize db:seed:all

# Inicie o servidor
npm run dev
```

A API estará disponível em `http://localhost:3001`

---

## 📄 Rotas da API

### 🔐 Autenticação
| Método | Rota | Descrição |
|--------|------|-----------|
| `POST` | `/users` | Cadastrar novo usuário |
| `POST` | `/sessions` | Login (retorna token JWT) |

### 🍔 Produtos
| Método | Rota | Descrição | Auth |
|--------|------|-----------|------|
| `GET` | `/products` | Listar todos os produtos | ✅ |
| `POST` | `/products` | Criar produto | Admin |
| `PUT` | `/products/:id` | Atualizar produto | Admin |
| `DELETE` | `/products/:id` | Deletar produto | Admin |

### 🗂️ Categorias
| Método | Rota | Descrição | Auth |
|--------|------|-----------|------|
| `GET` | `/categories` | Listar categorias | ✅ |
| `POST` | `/categories` | Criar categoria | Admin |

### 📦 Pedidos
| Método | Rota | Descrição | Auth |
|--------|------|-----------|------|
| `POST` | `/orders` | Criar pedido | ✅ |
| `GET` | `/orders` | Listar pedidos | Admin |
| `PUT` | `/orders/:id` | Atualizar status | Admin |

---

## 📁 Estrutura de Pastas

```
devburguer-back/
├── src/
│   ├── app/
│   │   ├── controllers/    # Lógica de cada rota
│   │   ├── middlewares/    # Auth JWT, validações
│   │   └── models/         # Modelos do Sequelize
│   ├── config/
│   │   └── database.js     # Configuração do banco
│   ├── database/
│   │   ├── migrations/     # Migrations do banco
│   │   └── seeds/          # Dados iniciais
│   └── routes.js           # Definição das rotas
├── .env.example
└── package.json
```

---

## 👨‍💻 Autor

Desenvolvido por **Joseph Augusto**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/joseph-august27/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Joseph24augusto27)

---

<div align="center">

Feito com 💜 durante o curso da [DevClub](https://devclub.com.br)

</div>
