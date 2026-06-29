# 🚀 Demo Django + Tailwind + Docker

Este repositório contém o código completo de um projeto desenvolvido passo a passo para a disciplina de Programação Web. O objetivo é construir uma aplicação web moderna e conteinerizada, abordando desde a criação da estrutura básica até a manipulação avançada de dados e rotas.

---

## 🛠️ Tecnologias Utilizadas

* **Backend:** Python (versão 3.12-slim) e Django (versão 5.1.3).
* **Frontend:** HTML5 e Tailwind CSS carregado via CDN.
* **Banco de Dados:** SQLite (banco local e leve).
* **Infraestrutura:** Docker e Docker Compose para isolamento do ambiente.

---

## ⚙️ Funcionalidades do Projeto Completo

* Ambiente de desenvolvimento padronizado e executado 100% via containers Docker.
* Página inicial dinâmica que lê e exibe mensagens armazenadas no banco de dados.
* Página estática adicional (`/sobre/`) para demonstrar o fluxo de roteamento do framework.
* Painel de administração nativo do Django ativado para gerenciamento de registros.
* Atualização de banco de dados via *migrations* (ex: adição do campo `autor` no modelo de mensagens).
* Arquitetura de código organizada estritamente no padrão MTV (Model-Template-View).

---

## 🚀 Como rodar o projeto na sua máquina

Certifique-se de ter o [Docker](https://docs.docker.com/get-docker/) instalado na sua máquina.

1. Faça o clone deste repositório e abra o seu terminal na pasta raiz do projeto (`demo-django`).
2. Suba a aplicação, construindo a imagem do container e aplicando as migrations automaticamente:
   `docker compose up --build`.
3. Acesse a página inicial pelo seu navegador no endereço: `http://localhost:8000`.
4. Acesse a página "Sobre" no endereço: `http://localhost:8000/sobre/`.

---

## 🔑 Acessando o Painel Admin

Para que as mensagens apareçam na tela inicial, você precisará criar e gerenciar o conteúdo através do painel de administração.

1. Com o projeto em execução, abra um **novo terminal** na pasta do projeto.
2. Execute o comando abaixo para criar o seu superusuário administrador:
   `docker compose exec web python manage.py createsuperuser`.
3. Preencha os dados solicitados no terminal (usuário, e-mail e senha).
4. Navegue até `http://localhost:8000/admin/`, faça login com os dados criados e acesse **Mensagens → Adicionar** para criar novos posts.

---

## 🛑 Comandos Úteis (Parando a aplicação)

* Para encerrar momentaneamente o servidor, aperte `Ctrl+C` no terminal que está rodando o `docker compose up`.
* Para derrubar completamente os containers e limpar o ambiente, execute o comando:
  `docker compose down`.