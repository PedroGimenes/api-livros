API de Biblioteca com FastAPI
1. Descrição do Projeto

Este projeto tem como objetivo desenvolver uma aplicação web para gerenciamento de livros, utilizando uma arquitetura composta por Front End, API e banco de dados.

A API será desenvolvida utilizando Python e FastAPI, permitindo realizar operações de cadastro, consulta, atualização e exclusão de livros. Os dados serão armazenados em um banco de dados MySQL, configurado e administrado por meio do XAMPP e phpMyAdmin.

O projeto também contará com um Front End desenvolvido com HTML, CSS e JavaScript, responsável por fornecer uma interface gráfica para que o usuário possa interagir com a API.

A comunicação entre o Front End e o Back End será realizada por meio de requisições HTTP utilizando a API fetch do JavaScript.

O desenvolvimento será realizado de forma incremental, dividido em quatro etapas:

Fundação;
Modelo e consultas;
CRUD completo;
Front End.

Durante todas as etapas será utilizado Git para controle de versão e GitHub para armazenamento do código e registro da evolução do projeto.

2. Objetivo Geral

Desenvolver uma aplicação completa de gerenciamento de livros, utilizando uma API REST construída com FastAPI, integrada a um banco de dados MySQL e posteriormente conectada a uma interface Front End desenvolvida com HTML, CSS e JavaScript.

O projeto tem como finalidade aplicar, de forma prática, conceitos de desenvolvimento de APIs, banco de dados, programação em Python, desenvolvimento Front End, integração entre sistemas e controle de versão.

3. Objetivos Específicos

Durante a realização do projeto, serão desenvolvidas as seguintes habilidades:

Criar uma API utilizando FastAPI;
Criar e organizar rotas da aplicação;
Utilizar os métodos HTTP GET, POST, PUT e DELETE;
Desenvolver uma API seguindo o conceito de CRUD;
Conectar uma aplicação Python a um banco de dados MySQL;
Utilizar o XAMPP para executar o servidor MySQL localmente;
Utilizar o phpMyAdmin para criar, visualizar e administrar o banco de dados;
Criar modelos de dados utilizando SQLAlchemy;
Criar schemas para entrada e saída de informações;
Utilizar Pydantic para validação de dados;
Criar sessões para comunicação com o banco de dados;
Realizar consultas, inserções, atualizações e exclusões;
Validar informações recebidas pela API;
Utilizar códigos de status HTTP adequados;
Implementar tratamento de erros;
Criar uma interface utilizando HTML;
Estilizar a interface utilizando CSS;
Desenvolver comportamentos e interações utilizando JavaScript;
Consumir uma API utilizando fetch;
Integrar o Front End ao Back End;
Utilizar o Source Control do Visual Studio Code;
Utilizar Git para controle de versão;
Utilizar GitHub para armazenar o projeto;
Registrar a evolução do projeto por meio de commits.
4. Tecnologias Utilizadas
Back End
Python
FastAPI
Uvicorn
SQLAlchemy
Pydantic
Banco de Dados
MySQL
XAMPP
phpMyAdmin
Front End
HTML5
CSS3
JavaScript
Fetch API
Controle de Versão
Git
GitHub
Source Control do Visual Studio Code
5. Arquitetura da Aplicação

A aplicação será organizada em três partes principais:

┌─────────────────────────────────────┐
│             FRONT END               │
│                                     │
│       HTML + CSS + JavaScript       │
│                                     │
└──────────────────┬──────────────────┘
                   │
                   │ HTTP / Fetch
                   │
                   ▼
┌─────────────────────────────────────┐
│               API                   │
│                                     │
│              FastAPI                │
│                                     │
│       GET / POST / PUT / DELETE     │
│                                     │
└──────────────────┬──────────────────┘
                   │
                   │ SQLAlchemy
                   │
                   ▼
┌─────────────────────────────────────┐
│           BANCO DE DADOS            │
│                                     │
│              MySQL                  │
│                                     │
│          biblioteca_db              │
│                                     │
└─────────────────────────────────────┘


O Front End será responsável pela interação com o usuário.

A API será responsável pelo processamento das requisições, validação dos dados e comunicação com o banco de dados.

O MySQL será responsável pelo armazenamento permanente das informações dos livros.

6. Estrutura do Projeto

A estrutura inicial do projeto poderá ser organizada da seguinte maneira:

biblioteca-api/
│
├── backend/
│   │
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   │
│   └── routes/
│       └── livros.py
│
├── frontend/
│   │
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── requirements.txt
├── .gitignore
└── README.md


Essa estrutura tem como objetivo separar as responsabilidades da aplicação e facilitar a manutenção e evolução do código.

7. Banco de Dados

O banco de dados utilizado será o MySQL, executado localmente por meio do XAMPP.

O banco de dados principal da aplicação será chamado:

biblioteca_db


Dentro desse banco será criada a tabela responsável pelo armazenamento dos livros:

livros


Uma estrutura inicial para a tabela poderá conter os seguintes campos:

Campo	Tipo	Descrição
id	INT	Identificador único do livro
titulo	VARCHAR	Título do livro
autor	VARCHAR	Autor do livro
ano	INT	Ano de publicação

O campo id será utilizado como identificador único de cada registro.

8. XAMPP e phpMyAdmin

O XAMPP será utilizado para disponibilizar o servidor MySQL no ambiente local de desenvolvimento.

O phpMyAdmin será utilizado como ferramenta para gerenciamento do banco de dados.

Por meio do phpMyAdmin será possível:

Criar o banco biblioteca_db;
Visualizar as tabelas;
Consultar os registros;
Inserir dados manualmente para testes;
Verificar alterações realizadas pela API;
Excluir registros;
Executar comandos SQL;
Conferir a estrutura das tabelas.

O banco de dados será utilizado pela aplicação FastAPI por meio de uma conexão configurada em Python.

9. Etapa 1 — Fundação
9.1 Objetivo

A primeira etapa terá como objetivo preparar o ambiente de desenvolvimento e estabelecer a base da aplicação.

Será criada a estrutura inicial do projeto, instaladas as dependências necessárias e configurada a comunicação entre a aplicação Python e o banco de dados MySQL.

9.2 Atividades

Nesta etapa serão realizadas as seguintes atividades:

Instalação e configuração do Python;
Criação do ambiente de desenvolvimento;
Criação do projeto FastAPI;
Instalação das bibliotecas necessárias;
Configuração do XAMPP;
Inicialização do MySQL;
Criação do banco biblioteca_db;
Configuração da conexão com o MySQL;
Criação do arquivo responsável pela conexão com o banco;
Criação do arquivo principal da aplicação;
Inicialização do servidor FastAPI;
Criação da rota de saúde da aplicação.
9.3 Dependências

As principais dependências utilizadas serão:

fastapi
uvicorn
sqlalchemy
pymysql
pydantic


As dependências poderão ser registradas no arquivo:

requirements.txt


Exemplo:

fastapi
uvicorn
sqlalchemy
pymysql
pydantic

9.4 Rota de Saúde

Será criada uma rota para verificar se a API está funcionando corretamente.

GET /health


Resposta esperada:

{
    "status": "ok"
}


Essa rota terá como finalidade facilitar a verificação inicial da aplicação.

9.5 Resultado da Etapa

Ao finalizar a primeira etapa, será possível:

Executar a API;
Acessar o servidor local;
Visualizar a documentação automática do FastAPI;
Confirmar que a API está funcionando;
Confirmar a conexão com o banco de dados;
Identificar a estrutura inicial do projeto.
10. Etapa 2 — Modelo e Consultas
10.1 Objetivo

A segunda etapa será dedicada à criação da estrutura de dados da aplicação e à implementação das primeiras operações relacionadas aos livros.

Será criado o modelo Livro, responsável por representar os registros armazenados no banco de dados.

Também serão criados os schemas responsáveis pela validação das informações recebidas e retornadas pela API.

10.2 Modelo Livro

O modelo Livro representará a tabela livros no banco de dados.

A estrutura conceitual será:

Livro
├── id
├── titulo
├── autor
└── ano


O modelo será utilizado pelo SQLAlchemy para realizar a comunicação entre o código Python e o banco de dados.

10.3 Schemas

Serão utilizados schemas para definir o formato dos dados que poderão ser enviados para a API.

Exemplo de dados para cadastro:

{
    "titulo": "Dom Casmurro",
    "autor": "Machado de Assis",
    "ano": 1899
}


Os schemas também serão utilizados para controlar os dados retornados pela API.

10.4 Sessão do Banco

Será criada uma configuração responsável por estabelecer sessões de comunicação com o MySQL.

Essa sessão permitirá que as rotas executem operações como:

Inserção;
Consulta;
Atualização;
Exclusão.

A utilização de sessões também permitirá controlar corretamente a abertura e o encerramento das conexões utilizadas pelas requisições.

10.5 Rota POST

Será criada a rota:

POST /livros


Sua finalidade será cadastrar um novo livro.

Exemplo de requisição:

{
    "titulo": "O Cortiço",
    "autor": "Aluísio Azevedo",
    "ano": 1890
}


Após a validação dos dados, o registro será armazenado no banco MySQL.

10.6 Rota GET

Será criada a rota:

GET /livros


Sua finalidade será retornar todos os livros cadastrados.

Também será criada uma rota para consulta individual:

GET /livros/{id}


Essa rota permitirá localizar um livro utilizando seu identificador.

10.7 Resultado da Etapa

Ao concluir a segunda etapa, a aplicação deverá ser capaz de:

Possuir um modelo de dados para livros;
Validar os dados utilizando schemas;
Conectar-se ao banco;
Cadastrar livros;
Listar livros;
Consultar livros individualmente.
11. Etapa 3 — CRUD Completo
11.1 Objetivo

A terceira etapa terá como objetivo completar as operações de gerenciamento dos livros.

Será implementado o CRUD completo da aplicação.

CRUD representa as quatro operações fundamentais:

Create  → Criar
Read    → Consultar
Update  → Atualizar
Delete  → Excluir

11.2 Rota PUT

Será criada a rota:

PUT /livros/{id}


Sua finalidade será atualizar as informações de um livro existente.

Exemplo:

{
    "titulo": "Dom Casmurro",
    "autor": "Machado de Assis",
    "ano": 1900
}


A API deverá verificar se o livro informado realmente existe antes de realizar a atualização.

11.3 Rota DELETE

Será criada a rota:

DELETE /livros/{id}


Essa rota será responsável por excluir um livro do banco de dados.

Antes da exclusão, a aplicação deverá verificar se o registro existe.

11.4 Tratamento de Erros

A API deverá tratar situações inesperadas e retornar respostas HTTP apropriadas.

Entre os casos que deverão ser tratados estão:

Livro inexistente;
ID inválido;
Dados enviados incorretamente;
Campos obrigatórios ausentes;
Erros de validação;
Problemas de comunicação com o banco de dados;
Requisições incompatíveis com as regras da aplicação.

Exemplo de resposta para um livro inexistente:

{
    "detail": "Livro não encontrado"
}


O código HTTP utilizado deverá representar corretamente o tipo de erro ocorrido.

Por exemplo:

200 OK
201 Created
204 No Content
400 Bad Request
404 Not Found
422 Unprocessable Entity
500 Internal Server Error

11.5 Testes do CRUD

Todas as operações deverão ser testadas individualmente.

Método	Endpoint	Operação
GET	/livros	Listar livros
GET	/livros/{id}	Buscar livro
POST	/livros	Criar livro
PUT	/livros/{id}	Atualizar livro
DELETE	/livros/{id}	Excluir livro

Os testes deverão verificar tanto situações de sucesso quanto situações de erro.

11.6 Resultado da Etapa

Ao finalizar a terceira etapa, a API deverá possuir um CRUD completo e funcional para gerenciamento dos livros.

12. Etapa 4 — Front End
12.1 Objetivo

A quarta etapa será dedicada à construção da interface visual da aplicação.

O objetivo será permitir que o usuário utilize as funcionalidades da API por meio de uma página web, sem precisar acessar diretamente os endpoints.

O Front End será desenvolvido utilizando:

HTML;
CSS;
JavaScript.
12.2 Estrutura HTML

O HTML será responsável pela estrutura da página.

A interface poderá possuir:

Formulário de cadastro;
Campos para título;
Campo para autor;
Campo para ano;
Botão de cadastro;
Área para listagem dos livros;
Botões de edição;
Botões de exclusão;
Área para mensagens ao usuário.
12.3 CSS

O CSS será utilizado para criar a aparência da aplicação.

Serão trabalhados aspectos como:

Organização dos elementos;
Espaçamento;
Cores;
Tipografia;
Formulários;
Botões;
Tabelas ou cards;
Responsividade;
Estados visuais da interface.

O objetivo será desenvolver uma interface simples, organizada e fácil de utilizar.

12.4 JavaScript

O JavaScript será responsável pela lógica do Front End.

Será utilizado para:

Capturar informações dos formulários;
Enviar dados para a API;
Buscar livros;
Atualizar a lista de livros;
Preencher informações para edição;
Excluir registros;
Exibir mensagens de sucesso;
Exibir mensagens de erro;
Atualizar a interface sem necessidade de recarregar a página.
12.5 Fetch API

A comunicação com o Back End será realizada utilizando fetch.

Exemplo de consulta:

fetch("http://localhost:8000/livros")
    .then(response => response.json())
    .then(data => {
        console.log(data);
    });


Para cadastro, será utilizada uma requisição POST:

fetch("http://localhost:8000/livros", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        titulo: "Dom Casmurro",
        autor: "Machado de Assis",
        ano: 1899
    })
});


O JavaScript será responsável por realizar a integração entre a interface e os endpoints da API.

12.6 Funcionalidades do Front End

A interface final deverá permitir ao usuário:

Cadastrar um novo livro;
Visualizar os livros cadastrados;
Buscar informações de um livro;
Editar informações;
Excluir livros;
Visualizar mensagens de sucesso;
Visualizar mensagens de erro;
Interagir com a API por meio de requisições HTTP.
12.7 Resultado da Etapa

Ao concluir a quarta etapa, a aplicação deverá possuir uma interface gráfica funcional integrada ao Back End.

O usuário poderá executar as operações do CRUD através do navegador.

13. Endpoints da API

Ao final do desenvolvimento, a API deverá possuir os seguintes endpoints:

Método	Endpoint	Descrição
GET	/health	Verifica se a API está funcionando
POST	/livros	Cadastra um livro
GET	/livros	Lista todos os livros
GET	/livros/{id}	Busca um livro pelo ID
PUT	/livros/{id}	Atualiza um livro
DELETE	/livros/{id}	Exclui um livro
14. Documentação da API

O FastAPI disponibiliza automaticamente uma documentação interativa da API.

Após iniciar o servidor, será possível acessar:

http://localhost:8000/docs


Essa documentação permitirá visualizar os endpoints e realizar testes diretamente pelo navegador.

Também poderá ser utilizada a documentação alternativa:

http://localhost:8000/redoc


A documentação será importante durante o desenvolvimento para verificar o comportamento de cada endpoint.

15. Execução do Projeto
15.1 Pré-requisitos

Para executar o projeto, será necessário possuir instalado:

Python;
XAMPP;
MySQL;
phpMyAdmin;
Git;
Visual Studio Code.
15.2 Criando o ambiente virtual

No terminal do projeto:

python -m venv venv


Para ativar no Windows:

venv\Scripts\activate

15.3 Instalando as dependências

Após ativar o ambiente virtual:

pip install -r requirements.txt

15.4 Iniciando o MySQL

No XAMPP, será necessário iniciar o serviço:

MySQL


Em seguida, o banco biblioteca_db deverá estar disponível no phpMyAdmin.

15.5 Executando a API

A aplicação poderá ser iniciada utilizando:

uvicorn backend.main:app --reload


Após iniciar, a API estará disponível em:

http://localhost:8000


A documentação poderá ser acessada em:

http://localhost:8000/docs

16. Controle de Versão

O Git será utilizado durante todo o desenvolvimento para acompanhar as alterações realizadas no projeto.

O Source Control do Visual Studio Code poderá ser utilizado para:

Visualizar arquivos modificados;
Conferir alterações;
Preparar arquivos para commit;
Criar commits;
Visualizar o histórico;
Sincronizar alterações com o GitHub.

O GitHub será utilizado como repositório remoto do projeto.

17. Organização dos Commits

Para facilitar o acompanhamento da evolução do projeto, os commits serão realizados de acordo com as funcionalidades implementadas.

Exemplos:

feat: cria estrutura inicial do projeto
feat: configura FastAPI
feat: configura conexão com MySQL
feat: cria banco biblioteca_db
feat: cria modelo Livro
feat: cria schemas de validação
feat: implementa rota POST de livros
feat: implementa rota GET de livros
feat: implementa rota PUT de livros
feat: implementa rota DELETE de livros
feat: adiciona tratamento de erros
test: realiza testes do CRUD
feat: cria estrutura do frontend
feat: implementa cadastro de livros
feat: implementa listagem de livros
feat: implementa edição de livros
feat: implementa exclusão de livros
feat: integra frontend com API
docs: atualiza README


Essa organização permitirá identificar de maneira clara o que foi desenvolvido em cada momento do projeto.

18. Fluxo de Desenvolvimento

O desenvolvimento seguirá o seguinte fluxo:

Etapa 1
Fundação
    │
    ├── Python
    ├── FastAPI
    ├── Dependências
    ├── XAMPP
    ├── MySQL
    └── Rota /health
    │
    ▼
Etapa 2
Modelo e Consultas
    │
    ├── Modelo Livro
    ├── Schemas
    ├── Sessão do banco
    ├── POST
    └── GET
    │
    ▼
Etapa 3
CRUD Completo
    │
    ├── PUT
    ├── DELETE
    ├── Validações
    ├── Tratamento de erros
    └── Testes
    │
    ▼
Etapa 4
Front End
    │
    ├── HTML
    ├── CSS
    ├── JavaScript
    ├── Fetch
    ├── Cadastro
    ├── Listagem
    ├── Edição
    └── Exclusão
    │
    ▼
Projeto Final
API + Banco de Dados + Interface Web

19. Critérios de Conclusão

O projeto será considerado concluído quando os seguintes requisitos forem atendidos:

API
 FastAPI configurado;
 Servidor funcionando;
 Rota /health implementada;
 Banco MySQL conectado;
 Modelo Livro criado;
 Schemas criados;
 Validação de dados implementada;
 Rota POST implementada;
 Rota GET implementada;
 Rota PUT implementada;
 Rota DELETE implementada;
 Tratamento de erros implementado;
 CRUD testado.
Banco de Dados
 XAMPP configurado;
 MySQL funcionando;
 Banco biblioteca_db criado;
 Tabela livros criada;
 Dados sendo persistidos corretamente;
 Banco verificado pelo phpMyAdmin.
Front End
 Página HTML criada;
 Estilos CSS implementados;
 JavaScript implementado;
 Formulário de cadastro criado;
 Listagem de livros implementada;
 Edição implementada;
 Exclusão implementada;
 API consumida utilizando fetch;
 Mensagens de sucesso e erro implementadas.
Versionamento
 Repositório Git configurado;
 Commits realizados durante o desenvolvimento;
 Source Control do VS Code utilizado;
 Projeto publicado no GitHub;
 README atualizado;
 Evolução do projeto registrada.
 
20. Objetivos Finais do Projeto

Ao final das quatro etapas, o projeto deverá apresentar uma aplicação completa capaz de realizar o gerenciamento de livros.

A aplicação deverá demonstrar a integração entre diferentes tecnologias:

HTML
  +
CSS
  +
JavaScript
  │
  │ Fetch
  ▼
FastAPI
  │
  │ SQLAlchemy
  ▼
MySQL
  │
  └── biblioteca_db


O objetivo principal é demonstrar, na prática, o desenvolvimento de uma aplicação desde a criação da estrutura inicial até sua integração completa entre Front End, Back End e banco de dados.

O projeto deverá evidenciar conhecimentos sobre criação de APIs REST, métodos HTTP, persistência de dados, validação, tratamento de erros, desenvolvimento de interfaces, consumo de APIs e controle de versão.

21. Considerações Finais

O desenvolvimento será realizado de forma progressiva, permitindo que cada etapa seja concluída e testada antes do início da próxima.

A primeira etapa estabelecerá a infraestrutura básica da aplicação. A segunda etapa será responsável pela criação dos modelos e das primeiras operações com livros. A terceira etapa completará o CRUD e adicionará validações, tratamento de erros e testes. Por fim, a quarta etapa será responsável pela criação do Front End e pela integração da interface com a API.

Dessa maneira, o projeto terá como resultado uma aplicação web completa de gerenciamento de livros, utilizando FastAPI no Back End, MySQL para persistência dos dados e HTML, CSS e JavaScript no Front End, além de Git e GitHub para controle e acompanhamento da evolução do desenvolvimento.