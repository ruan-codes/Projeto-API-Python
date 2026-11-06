# 🛒 API de E-commerce

API REST em Flask para um e-commerce: gestão de produtos, autenticação de usuários e carrinho de compras.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=FFD43B)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)

## Funcionalidades

- CRUD de produtos
- Login e logout com Flask-Login; rotas de escrita protegidas
- Carrinho por usuário: adicionar, remover, listar e finalizar compra (checkout com total)
- Documentação no formato Swagger em `DocumentoSwaggerAPIRocketseat.x-yaml`

## Tecnologias

Python · Flask · Flask-SQLAlchemy · Flask-Login · Flask-CORS · SQLite · Postman

## Endpoints

| Método | Rota | Auth | Descrição |
|---|---|:---:|---|
| `POST` | `/login` | | Autentica o usuário |
| `POST` | `/logout` | 🔒 | Encerra a sessão |
| `GET` | `/api/products` | | Lista os produtos |
| `GET` | `/api/products/<id>` | | Detalha um produto |
| `POST` | `/api/products/add` | 🔒 | Cadastra um produto |
| `PUT` | `/api/products/update/<id>` | 🔒 | Atualiza um produto |
| `DELETE` | `/api/products/delete/<id>` | 🔒 | Remove um produto |
| `GET` | `/api/cart` | 🔒 | Lista o carrinho |
| `POST` | `/api/cart/add/<id>` | 🔒 | Adiciona ao carrinho |
| `DELETE` | `/api/cart/remove/<id>` | 🔒 | Remove do carrinho |
| `POST` | `/api/cart/checkout` | 🔒 | Finaliza a compra |

## Como rodar

```bash
git clone https://github.com/ruan-codes/Projeto-API-Python.git
cd Projeto-API-Python

python -m venv venv
venv\Scripts\activate          # Windows
# source venv/bin/activate     # Linux/macOS

pip install flask flask-sqlalchemy flask-login flask-cors
python app.py
```

A API sobe em `http://127.0.0.1:5000`. O banco `instance/ecommerce.db` já vem no repositório.

A API não tem rota de cadastro, então crie um usuário pelo terminal antes de fazer login:

```bash
python -c "from app import app, db, User; app.app_context().push(); db.session.add(User(username='admin', password='123')); db.session.commit()"
```

Depois faça `POST /login` com `{"username": "admin", "password": "123"}` e teste as rotas no Postman.
