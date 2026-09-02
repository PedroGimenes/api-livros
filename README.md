# 📚 Biblioteca API — FastAPI + MySQL

Projeto desenvolvido para praticar a criação de uma API REST completa utilizando **FastAPI**, com persistência de dados em **MySQL** (via XAMPP/phpMyAdmin) e uma interface web construída com **HTML, CSS e JavaScript** puro.

O projeto simula o gerenciamento de um acervo de livros, permitindo cadastrar, listar, editar e excluir registros através de uma API RESTful e de uma interface visual que consome essa API.

---

## 🎯 Objetivos do Projeto

* Criar rotas com **FastAPI**
* Utilizar os métodos HTTP `GET`, `POST`, `PUT` e `DELETE`
* Conectar Python a um banco de dados **MySQL**
* Utilizar **XAMPP** e **phpMyAdmin** para gerenciar o banco
* Criar **modelos** (SQLAlchemy) e **schemas** (Pydantic)
* Validar dados e tratar **erros HTTP**
* Construir interfaces com **HTML, CSS e JavaScript**
* Consumir a API utilizando `fetch`
* Utilizar o **Source Control** do VS Code
* Registrar a evolução do projeto no **GitHub**


---

## 🛠️ Tecnologias Utilizadas

| Categoria | Ferramenta |
|---|---|
| Linguagem | Python 3.x |
| Framework Web | FastAPI |
| Servidor ASGI | Uvicorn |
| ORM | SQLAlchemy |
| Validação de dados | Pydantic |
| Banco de dados | MySQL (via XAMPP) |
| Administração do banco | phpMyAdmin |
| Driver MySQL | PyMySQL |
| Front-end | HTML5, CSS3, JavaScript (fetch API) |
| Controle de versão | Git + GitHub (VS Code Source Control) |

---

## 📁 Estrutura do Projeto

```
biblioteca-api/
│
├── app/
│   ├── main.py            # Instância do FastAPI e rotas
│   ├── database.py        # Conexão com o MySQL (engine, session)
│   ├── models.py          # Modelos SQLAlchemy (tabela livros)
│   ├── schemas.py         # Schemas Pydantic (validação de entrada/saída)
│   └── crud.py            # Funções de CRUD (create, read, update, delete)
│
├── static/
│   ├── index.html          # Interface web
│   ├── style.css           # Estilização
│   └── script.js           # Consumo da API via fetch
│
├── requirements.txt        # Dependências do projeto
└── README.md                # Este arquivo
```

---

## ⚙️ Pré-requisitos

* [Python 3.10+](https://www.python.org/)
* [XAMPP](https://www.apachefriends.org/) (com MySQL e phpMyAdmin ativos)
* [VS Code](https://code.visualstudio.com/)
* Git instalado e configurado

---

## 🚀 Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/biblioteca-api.git
cd biblioteca-api
```

### 2. Criar e ativar o ambiente virtual

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

Principais pacotes utilizados:

```
fastapi
uvicorn
sqlalchemy
pymysql
pydantic
```

### 4. Iniciar o XAMPP

* Abra o **XAMPP Control Panel**
* Inicie os módulos **Apache** e **MySQL**

### 5. Criar o banco de dados no phpMyAdmin

* Acesse [http://localhost/phpmyadmin](http://localhost/phpmyadmin)
* Crie um novo banco de dados chamado **`biblioteca_db`**
* As tabelas serão criadas automaticamente pelo SQLAlchemy ao iniciar a API

### 6. Rodar a API

```bash
uvicorn app.main:app --reload
```

* Documentação interativa (Swagger): [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
* Documentação alternativa (ReDoc): [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

### 7. Abrir a interface web

Abra o arquivo `static/index.html` no navegador (ou sirva via extensão Live Server do VS Code) para cadastrar, listar, editar e excluir livros pela interface gráfica.

---

## 🧱 Etapas de Desenvolvimento

O projeto foi construído em **4 etapas**, cada uma registrada como um marco de evolução no GitHub através do Source Control do VS Code.

### 🔹 Etapa 1 · Fundação

Preparação do ambiente, dependências, banco `biblioteca_db`, conexão com MySQL e rota de saúde.

* Criação do ambiente virtual e instalação das dependências
* Criação do banco `biblioteca_db` via XAMPP/phpMyAdmin
* Configuração da conexão do SQLAlchemy com o MySQL (`database.py`)
* Criação da rota de verificação de saúde da API (`/health` ou `/`)
* Primeiro commit no GitHub com a estrutura inicial do projeto

### 🔹 Etapa 2 · Modelo e Consultas

Criação do modelo `Livro`, schemas, sessão do banco e rotas `POST` e `GET`.

* Definição do modelo `Livro` (SQLAlchemy) com campos como `id`, `titulo`, `autor`, `ano`, `genero`
* Criação dos schemas Pydantic para entrada (`LivroCreate`) e saída (`LivroResponse`)
* Configuração da sessão do banco (`get_db`) via dependência do FastAPI
* Implementação da rota `POST /livros` para cadastro
* Implementação da rota `GET /livros` (listagem) e `GET /livros/{id}` (consulta individual)

### 🔹 Etapa 3 · CRUD Completo

Implementação das rotas `PUT` e `DELETE`, tratamento de erros e testes do CRUD.

* Implementação da rota `PUT /livros/{id}` para atualização de registros
* Implementação da rota `DELETE /livros/{id}` para exclusão
* Tratamento de erros HTTP (`404 Not Found`, `400 Bad Request`, `422 Unprocessable Entity`) usando `HTTPException`
* Validações adicionais nos schemas Pydantic
* Testes completos do CRUD via Swagger (`/docs`)

### 🔹 Etapa 4 · Front-End

Construção da interface com HTML, CSS e JavaScript para cadastrar, listar, editar e excluir livros.

* Criação da estrutura HTML da interface (formulário + tabela/lista de livros)
* Estilização com CSS
* Consumo da API via JavaScript (`fetch`), cobrindo os métodos `GET`, `POST`, `PUT` e `DELETE`
* Atualização dinâmica da interface sem recarregar a página
* Commit final documentando a conclusão do projeto

---

## 🔗 Rotas da API

| Método | Rota | Descrição |
|---|---|---|
| `GET` | `/` | Rota de saúde/status da API |
| `GET` | `/livros` | Lista todos os livros |
| `GET` | `/livros/{id}` | Retorna um livro específico |
| `POST` | `/livros` | Cadastra um novo livro |
| `PUT` | `/livros/{id}` | Atualiza um livro existente |
| `DELETE` | `/livros/{id}` | Remove um livro |

---

## 🌿 Controle de Versão

O versionamento foi feito utilizando o **Source Control** integrado do VS Code, com commits organizados por etapa de desenvolvimento, refletindo a evolução do projeto:

```bash
git add .
git commit -m "Etapa 1: fundação e conexão com o banco"
git push origin main
```

Esse padrão se repete a cada etapa concluída, mantendo um histórico claro no GitHub.

---

## 👤 Autor

Projeto desenvolvido como exercício prático de back-end com FastAPI e integração front-end/back-end.