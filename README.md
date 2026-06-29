# Projeto Demo: Django + Tailwind + Docker (Parte II)

Este projeto é a continuação do desenvolvimento de um site simples construído com **Django**, estilizado com **Tailwind CSS** (via CDN), utilizando **SQLite** como banco de dados e executado em um container **Docker**. 

---

## 🚀 Funcionalidades Implementadas

* Gerenciamento de mensagens diretamente pelo painel administrativo nativo do Django.
* Adição de novos campos no banco de dados (como o campo `autor`) utilizando o sistema de *migrations* do Django.
* Criação de uma nova página estática "Sobre" (`/sobre/`), interligada através da criação de novas rotas, views e templates.
* Atualização da interface visual modificando as classes utilitárias do Tailwind CSS diretamente no HTML.
* Implementação estruturada baseada no padrão de projeto MTV (Model-Template-View).

---

## ⚙️ Como executar o projeto

1. Para construir a imagem (caso seja a primeira vez ou haja mudanças no `Dockerfile`) e iniciar o servidor, execute no terminal: 
   `docker compose up --build`.
2. Com o servidor iniciado, acesse a página principal pelo navegador no endereço: `http://localhost:8000`.
3. Para acessar a página "Sobre", navegue até: `http://localhost:8000/sobre/`.
4. Para parar a execução do servidor, utilize o atalho `Ctrl+C` no terminal ativo.
5. Para remover os containers gerados pelo projeto, execute: `docker compose down`.

---

## 🔑 Acesso ao Painel Administrativo

Para que você consiga cadastrar, visualizar e gerenciar as mensagens no site, é preciso criar um usuário superadministrador.

1. Mantenha o servidor rodando, abra um **segundo terminal** na mesma pasta do projeto e execute o comando:
   `docker compose exec web python manage.py createsuperuser`.
2. Siga as instruções na tela preenchendo um nome de usuário, e-mail (opcional) e uma senha.
3. No seu navegador, acesse o painel pelo link `http://localhost:8000/admin/` e faça login com as credenciais criadas.
4. No painel, vá em **Mensagens → Adicionar** para inserir um novo registro e vê-lo refletido imediatamente na página principal.

---

## 📂 Fluxo MTV (Model-Template-View)

O funcionamento interno desta aplicação segue rigorosamente o padrão MTV, que define como os componentes do Django interagem:

| Componente | Arquivo/Responsabilidade | O que faz no projeto |
| :--- | :--- | :--- |
| **Model** | `home/models.py` | Define a estrutura dos dados; o ORM do Django converte isso para código SQL lido pelo banco SQLite. |
| **Template** | `templates/home/index.html` | Arquivos HTML responsáveis pela apresentação visual dos dados ao usuário. |
| **View** | `home/views.py` | Contém as funções lógicas que recebem as requisições, consultam o banco (Models) e renderizam os dados na tela (Templates). |
| **Urls (Rotas)** | `home/urls.py` | Intercepta o link acessado pelo navegador e encaminha para a respectiva View (ex: `/sobre/` chama a função `sobre`). |