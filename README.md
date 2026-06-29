# Projeto Demo: Django + Tailwind + Docker

Este é um projeto de demonstração simples, consistindo em um site de uma única página construído do zero. O objetivo principal foi criar uma aplicação web moderna e conteinerizada, facilitando a execução em qualquer ambiente sem a necessidade de configurações complexas na máquina local.

---

## 🛠️ Tecnologias Utilizadas

* **Django**: Framework web em Python utilizado na versão 5.1.3.
* **Python**: Linguagem base do projeto, rodando na versão 3.12-slim dentro do container.
* **Tailwind CSS**: Framework CSS utility-first, carregado diretamente via CDN para estilização.
* **Banco de Dados**: SQLite, utilizado localmente para armazenar as informações.
* **Docker e Docker Compose**: Ferramentas utilizadas para orquestrar e isolar o ambiente de desenvolvimento.

---

## ⚙️ Funcionalidades

* Exibição de uma página inicial estilizada com Tailwind CSS.
* Listagem dinâmica de mensagens cadastradas no banco de dados.
* Painel administrativo do Django integrado e pronto para uso.
* Atualização em tempo real das alterações de código graças ao mapeamento de volumes no Docker.

---

## 🚀 Como executar o projeto

Certifique-se de ter o [Docker](https://docs.docker.com/get-docker/) instalado na sua máquina.

1. Faça o clone deste repositório em seu ambiente local.
2. Abra o terminal na raiz da pasta do projeto (`demo-django`).
3. Execute o comando `docker compose up --build` para construir a imagem e subir o servidor.
4. O container aplicará automaticamente as migrations no banco SQLite na inicialização.
5. Abra o seu navegador e acesse `http://localhost:8000` para visualizar a página.
6. Para acessar o painel de administração, vá até `http://localhost:8000/admin/` e gerencie as mensagens do banco de dados.

---

## 🛑 Como parar a execução

Para interromper o servidor, utilize o atalho `Ctrl+C` no terminal onde ele está rodando.

Para remover os containers e limpar o ambiente, execute o comando `docker compose down`.

---

## 📝 Notas de Desenvolvimento

Este projeto foi desenvolvido como parte de uma atividade de Programação Web. O código base da primeira etapa foi versionado na branch `bcc481-django-parte1`, conforme as instruções de entrega do roteiro.