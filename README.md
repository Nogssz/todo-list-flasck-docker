# 📋 To-Do List Flask com Docker e Nginx (SSL)

Projeto de uma aplicação web simples que permite criar, editar, concluir e deletar tarefas. Desenvolvido em Flask (Python), rodando com Gunicorn, Nginx (proxy reverso) e certificado SSL autoassinado, tudo configurado em containers Docker.

---

## 🚀 Tecnologias usadas

- **Backend:** Python, Flask
- **Banco de Dados:** SQLite
- **Frontend:** HTML, CSS
- **Docker e Docker Compose**
- **Gunicorn**
- **Nginx (Proxy Reverso com SSL autoassinado)**

## 🛠️ Como executar localmente

### ⚠️ Pré-requisitos

Antes de iniciar, você deve ter instalado:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Docker e Docker Compose já integrados)
- Temos no final do README as dependências Python caso não funcione e instale fora do DOCKER.
---

### ▶️ Rodando a aplicação

**1. Clone o repositório**

```bash
git clone https://github.com/Nogssz/todo-list-flasck-docker.git
```

**2. Entre na pasta do projeto:**

```cd todo-list-flasck-docker```

**3. Inicialize os certificados SSL autoassinados primeiro**

```docker compose up -d cert-generator```

**4. docker compose up -d cert-generator**
Nessa parte espera cerca de 20 segundo até os certificado serem gerados em certs/ (abra a pasta
e veja se foi criado dois arquivos la dentro)
certs/
├── fullchain.pem
└── privkey.pem

**5. Agora suba a aplicação Flask e o Nginx**

```docker compose up -d --build```

🌐 Acesse a aplicação no navegador
Agora você pode acessar através das URLs:

HTTP: http://localhost
HTTPS: https://localhost

🛑 Parar aplicação e remover containers:

```docker compose down```

📦 Dependências Python
Para instalar ou atualizar dependências localmente (fora do Docker):

Criar ambiente virtual:

python -m venv .venv
# Windows (Git Bash)
source .venv/Scripts/activate
# Linux/Mac
source .venv/bin/activate

pip install -r requirements.txt

pip install nome-da-dependencia
pip freeze > requirements.txt


