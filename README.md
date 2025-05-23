# 📁 Gestor de Projetos

**Gestor de Projetos** é uma aplicação Django estruturada em arquitetura de **microserviços**, voltada para o **gerenciamento institucional de projetos**, incluindo tarefas, atores, órgãos e autenticação.  
A API é **RESTful** e suporta autenticação via **JWT**, além de login tradicional por sessão.

---

## 🧩 Estrutura do Projeto

```
projeto/
├── manage.py
├── projeto/                    ← Projeto principal do Django
├── auth_manager_api/           ← Módulo de autenticação (JWT & Sessions)
├── sistema_auth/               ← Suporte à autenticação local
├── projeto_service/            ← Módulo de projetos
├── tarefa_service/             ← Módulo de tarefas       
├── atores_service/             ← Módulo de atores/papéis
├── orgao_service/              ← Módulo de órgãos
├── templates/                  
├── db.sqlite3
└── requirements.txt
```

---

## 🛠️ Requisitos

- Python 3.10+
- pip
- Git

---

## ⚙️ Instalação

```bash
git clone https://github.com/JoaoVictorCarvalho-DEV/API_User_Django.git
cd API_User_Django
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

---

## 🚀 Execução

```bash
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Acesse: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🔐 Autenticação

- Modelo customizado: `auth_manager_api.CustomUser`
- Suporte a:
  - Autenticação por sessão (`SessionAuthentication`)
  - Autenticação por token (`JWT via djangorestframework-simplejwt`)

---

## 🔁 Endpoints Principais

| Caminho                       | Descrição                        |
|------------------------------|----------------------------------|
| `/admin/`                    | Painel administrativo do Django  |
| `/site/auth/`                | Tela de login/autenticação       |
| `/site/projetos/`            | Módulo de gerenciamento de projetos |
| `/site/tarefas/`             | Módulo de tarefas                |
| `/site/atores/`              | Módulo de atores e papéis        |
| `/site/orgaos/`              | Módulo de órgãos institucionais  |
| `/auth_api/`                 | API de autenticação via JWT      |
| `/api/v1/`                   | API REST geral (DRF router)      |

---

## 📄 Documentação OpenAPI

- Esquema: [http://127.0.0.1:8000/api/schema/](http://127.0.0.1:8000/api/schema/)
- Swagger UI (se habilitado): [http://127.0.0.1:8000/api/docs/](http://127.0.0.1:8000/api/docs/)

Configuração:
```python
SPECTACULAR_SETTINGS = {
    'TITLE': 'Auth & Projects API',
    'DESCRIPTION': 'API criada para ser um serviço de gerenciamento de projetos.',
    'VERSION': '1.0.0',
}
```

---

## 🌐 Localização e Fuso Horário

```python
LANGUAGE_CODE = 'pt-br'
TIME_ZONE = 'America/Sao_Paulo'
```

---

## 🧾 Banco de Dados

- Desenvolvimento:
```python
ENGINE = 'django.db.backends.sqlite3'
```

- Produção recomendada: PostgreSQL ou outro banco relacional robusto.

---

## 🔐 Segurança

Recomendações para ambiente de produção:
```python
DEBUG = False
SECRET_KEY = os.environ.get('DJANGO_SECRET_KEY')
'DEFAULT_PERMISSION_CLASSES': [
    'rest_framework.permissions.IsAuthenticated',
]
```

---

## 🗂 Modularização por App

```
auth_manager_api/    ← Autenticação e criação de usuários
projeto_service/     ← CRUD de projetos
tarefa_service/      ← CRUD de tarefas
atores_service/      ← Atores, papéis e permissões
orgao_service/       ← Órgãos e setores institucionais
```

---

## 📌 Status do Projeto

🚧 Em desenvolvimento  
Funcionalidades básicas de CRUD e autenticação já implementadas.

---

## 📜 Licença

Este projeto está licenciado sob os termos da **MIT License**.

---
