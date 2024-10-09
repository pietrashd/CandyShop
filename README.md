# Candy Shop

## Descrição

O **Candy Shop** é uma aplicação web completa que simula uma loja online de doces mágicos. Os usuários podem explorar e cadastrar produtos, adicionar ao carrinho, favoritar itens, e se cadastrar ou fazer login para realizar compras. A aplicação é composta por um frontend interativo e um backend que gerencia dados de usuários e produtos com integração ao banco de dados MySQL.

## Instalação

### Backend

O backend é desenvolvido com Node.js e utiliza Express e MySQL para fornecer serviços de API e gerenciamento de dados.

1. Acesse o diretório `backend`.
2. Instale as dependências:
   ```bash
   npm install
   ```
3. Inicie o servidor:
   ```bash
   npm start
   ```

O servidor estará rodando com o auxílio do `nodemon` e atenderá às requisições feitas pelo frontend.

### Frontend

O frontend está localizado na pasta `Candy Shop`. Para rodar o site, basta abrir o arquivo `index.html` no navegador.

## Banco de Dados

O banco de dados utilizado é MySQL. As tabelas principais são as seguintes:

- **Tabela de Usuários (`usuario`)**:
  - Campos:
    - `id_usuario`: Chave primária.
    - `email`: Email único do usuário.
    - `NomeCompleto`: Nome completo do usuário.
    - `senha`: Senha para login.
    - `perfil`: Enum com valores 'admin' ou 'usuario'.
  - Exemplo de inserção de usuário:
    ```sql
    INSERT INTO usuario (email, NomeCompleto, senha, perfil)
    VALUES ('Alana@gmail.com', 'Alana', '1455', 'admin');
    ```

- **Tabela de Produtos (`produtos`)**:
  - Campos:
    - `id_produto`: Chave primária.
    - `nomeProduto`: Nome único do produto.
    - `preco`: Preço do produto.
    - `descricao`: Descrição do produto.
  - Exemplo de inserção de produto:
    ```sql
    INSERT INTO produtos (nomeProduto, preco, descricao)
    VALUES ('Bolacha Suprema', 48, 'Bolacha que recupera saúde física e mental');
    ```

O arquivo `SQL Candy-Shop.sql` contém o script SQL completo para a criação e manutenção dessas tabelas.

## Funcionalidades

- **Carregamento Dinâmico de Produtos**: A aplicação exibe uma lista de produtos com nome, preço e imagem.
- **Sistema de Carrinho**: Os usuários podem adicionar produtos ao carrinho de compras, que é atualizado dinamicamente.
- **Autenticação de Usuário**: O backend permite login e registro de novos usuários.
- **Favoritar Produtos**: Opção de favoritar produtos para acesso rápido.
- **Cadastrar Produtos**: Perfis de Admins podem cadastrar novos produtos no site.

## Rotas da API

Aqui estão as principais rotas do backend, que podem ser importadas no Postman para facilitar o uso e teste:

- **POST /api/login**: Realiza o login de um usuário.
  - Body (JSON):
    ```json
    {
      "email": "usuario@gmail.com",
      "senha": "senha123"
    }
    ```

- **POST /api/register**: Registra um novo usuário.
  - Body (JSON):
    ```json
    {
      "NomeCompleto": "Novo Usuário",
      "email": "novo@gmail.com",
      "senha": "senha123"
    }
    ```

- **GET /api/produtos**: Retorna a lista de produtos disponíveis.

- **POST /api/carrinho**: Adiciona um produto ao carrinho.
  - Body (JSON):
    ```json
    {
      "id_produto": 1,
      "quantidade": 2
    }
    ```

Você pode baixar a coleção do Postman com essas rotas através do link:

[Baixar coleção do Postman](sandbox:/mnt/data/Candy-Shop/postman_collection.json)

## Estrutura de Arquivos

- **index.html**: Página principal do site.
- **script.js**: Gerencia as funcionalidades do frontend (carrinho, favoritar, etc.).
- **styles.css**: Define o estilo visual do site.
- **Login**: Contém arquivos para o sistema de login.
- **SQL Candy-Shop.sql**: Script de criação das tabelas do banco de dados.
  
## Dependências

- **Backend**:
  - express: ^4.19.2
  - cors: ^2.8.5
  - mysql2: ^3.11.0
  - nodemon: ^3.1.4

## Executando o Projeto

1. Configure o banco de dados MySQL conforme o script fornecido.
2. Inicie o backend com `npm start`.
3. Abra o `index.html` no navegador para interagir com o frontend.
