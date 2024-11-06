# **Web Service RESTful com Flask e SQLAlchemy**

O REST é uma alternativa mais leve ao SOAP, baseado em operações HTTP. Ele é implementado em Python usando Flask e SQLAlchemy, que simplificam a criação de APIs RESTful.

## Configuração do Servidor RESTful

### *Flask*
Um framework leve para a criação de servidores, configurado para responder a solicitações HTTP.

### *SQLAlchemy*
Biblioteca ORM para gerenciar o banco de dados, configurada para persistir dados no PostgreSQL.

### *Exemplo de Operações REST*
- **GET**: Recupera dados dos temas e módulos.
- **POST**: Adiciona novos temas e módulos.
- **DELETE**: Remove temas ou módulos, conforme a solicitação.

## Cliente REST

Para consumir o Web Service RESTful, utiliza-se a biblioteca `requests`. Este cliente acessa as URIs dos recursos e executa operações HTTP, como listar, inserir ou excluir dados, com base nas rotas configuradas no servidor.