# Ag_8_Ds_II
---
marp: true
theme: default
paginate: true
header: 'Programação Web II | Projeto Final'
footer: 'Apresentação: Gabi | Orientadora: Prof.ª Alice'
---

# 🚀 Sistema de Cadastro de Amigos (CRUD)
### Com Autenticação de Usuários

**Estudante:** Gabi  
**Orientadora:** Prof.ª Alice  
**Disciplina:** Programação Web II  

---

## 📌 Visão Geral do Projeto

- **Objetivo:** Sistema Web seguro para gerenciamento de contatos pessoais.
- **Diferencial:** Acesso restrito por usuário via autenticação.

### Stack Tecnológica
- **Front-end:** HTML5, CSS3, JavaScript (Fetch API / Async-Await)
- **Back-end:** Node.js + Express
- **Banco de Dados:** MySQL / PostgreSQL
- **Segurança:** JSON Web Tokens (JWT) & bcrypt

---

## 🔒 Módulo de Autenticação e Segurança

1. **Validação de Senha:** Comparação via bcrypt.
2. **Geração do Token:** Emissão de JWT assinado após validação.
3. **Autorização:** Token enviado em cada requisição protegida (`Authorization: Bearer <TOKEN>`).

---

## 📊 Rotas da API RESTful (CRUD)

| Método | Endpoint | Ação | Autenticado? |
| :--- | :--- | :--- | :---: |
| `POST` | `/api/login` | Realiza login do usuário | Não |
| `POST` | `/api/amigos` | Cadastra novo amigo | **Sim** |
| `GET` | `/api/amigos` | Lista amigos do usuário | **Sim** |
| `PUT` | `/api/amigos/:id` | Atualiza dados do amigo | **Sim** |
| `DELETE` | `/api/amigos/:id` | Remove amigo cadastrado | **Sim** |

---

## 🗄️ Modelo de Banco de Dados

### Tabela `usuarios`
- `id` (PK, INT, Auto Increment)
- `email` (VARCHAR, Unique)
- `senha_hash` (VARCHAR)

### Tabela `amigos`
- `id` (PK, INT, Auto Increment)
- `usuario_id` (FK -> `usuarios.id`)
- `nome` (VARCHAR)
- `telefone` (VARCHAR)
- `email` (VARCHAR)

---

## 🎬 Demonstração Prática

- 🎥 **Vídeo 1:** Login e validação de erros de acesso
- 🎥 **Vídeo 2:** Cadastro e listagem dinâmica de amigos
- 🎥 **Vídeo 3:** Edição e exclusão de registros em tempo real

---

## 💡 Desafios Técnicos e Aprendizados

- Controle de sessão *stateless* com **JWT**.
- Tratamento de status HTTP (`200 OK`, `201 Created`, `401 Unauthorized`, `404 Not Found`).
- Organização de arquitetura em padrão **MVC**.

---

# 🤝 Obrigado!

Agradecimentos especiais à **Prof.ª Alice** e a todo o corpo docente.
