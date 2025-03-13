# 📋 To-Do List Flask com Docker e Nginx (SSL)

Este projeto consiste em uma aplicação web simples que permite criar, concluir e deletar tarefas. Desenvolvida utilizando Flask (Python), Gunicorn, Nginx como proxy reverso e certificados SSL autoassinados, tudo configurado em containers Docker.

---

## 🚀 Tecnologias Utilizadas

- **Backend:** Python (Flask)
- **Banco de Dados:** SQLite
- **Frontend:** HTML, CSS
- **Servidor Web:** Gunicorn
- **Proxy Reverso:** Nginx (com SSL autoassinado)
- **Conteinerização:** Docker e Docker Compose

---

## 🛠️ Como executar localmente

### ⚠️ Pré-requisitos

Antes de começar, instale:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Docker e Docker Compose já integrados)

> Ao final deste README estão instruções adicionais para instalação manual das dependências Python, caso necessário.

### ▶️ Passos para execução

**1. Clone o repositório**

```bash
git clone https://github.com/Nogssz/todo-list-flasck-docker.git
```

**2. Entre no diretório do projeto:**

```bash
cd todo-list-flasck-docker
```

**3. Gere os certificados SSL autoassinados (necessário somente na primeira execução):**

```bash
docker compose up -d cert-generator
```

Aguarde cerca de 20 segundos até que os certificados sejam gerados no diretório `certs/`:

```text
certs/
├── fullchain.pem
└── privkey.pem
```

**4. Suba a aplicação Flask juntamente com o Nginx:**

```bash
docker compose up -d --build
```

### 🌐 Acesse a aplicação no navegador

- **HTTP:** [http://localhost](http://localhost)
- **HTTPS:** [https://localhost](https://localhost) (aceite o aviso de segurança do certificado autoassinado)

### 🛑 Para parar a aplicação e remover os containers:

```bash
docker compose down
```

---

## 📦 Dependências Python

Caso precise instalar ou atualizar as dependências localmente (fora do Docker):

**Crie um ambiente virtual:**

```bash
python -m venv .venv
# Windows (Git Bash)
source .venv/Scripts/activate
# Linux/Mac
source .venv/bin/activate
```

**Instale as dependências:**

```bash
pip install -r requirements.txt
```

**Adicionar novas dependências:**

```bash
pip install nome-da-dependencia
pip freeze > requirements.txt
```

---

## 🤝 Contribuições e dúvidas

Contribuições são muito bem-vindas! Se tiver dúvidas ou sugestões, abra uma issue ou entre em contato diretamente.

Desenvolvido por [Nogssz](https://github.com/Nogssz) 🚀😊
