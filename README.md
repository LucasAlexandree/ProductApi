
# ProductApi

Este projeto é uma API RESTful simples para o gerenciamento de produtos, implementada usando .NET Core e Entity Framework Core. A API permite realizar operações básicas de CRUD (Criar, Ler, Atualizar e Deletar) para produtos.

## Requisitos

- .NET 6 ou superior
- SQL Server (ou banco de dados relacional de sua escolha)

## Funcionalidades

A API oferece os seguintes endpoints para o gerenciamento de produtos:

- **GET /api/products**: Retorna a lista de todos os produtos.
- **POST /api/products**: Cria um novo produto.
- **GET /api/products/{id}**: Retorna um produto específico por ID.
- **PUT /api/products/{id}**: Atualiza um produto existente.
- **DELETE /api/products/{id}**: Deleta um produto.

Cada produto tem as seguintes propriedades:
- `ProductID`: Identificador único do produto (gerado automaticamente).
- `Name`: Nome do produto (obrigatório).
- `Price`: Preço do produto (obrigatório, deve ser maior que zero).
- `StockQuantity`: Quantidade disponível em estoque (obrigatório, deve ser maior ou igual a zero).

## Como Rodar o Projeto Localmente

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/ProductApi.git
```

### 2. Navegue até o diretório do projeto

```bash
cd ProductApi
```

### 3. Restaure as dependências

```bash
dotnet restore
```

### 4. Configure a conexão com o banco de dados

No arquivo `appsettings.json`, configure a string de conexão para o banco de dados SQL Server ou outro banco de sua escolha:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=ProductDb;Trusted_Connection=True;"
  }
}
```

### 5. Execute as migrações (caso esteja utilizando Entity Framework)


### 6. Execute a aplicação



A aplicação será iniciada em `http://localhost:5000` ou `https://localhost:5001`, dependendo de sua configuração.

## Como Testar a API

### 1. Acesse o Swagger

Após iniciar a aplicação, abra o navegador e vá até o seguinte endereço para acessar o Swagger UI:

```
http://localhost:5000/swagger
```

ou, se estiver utilizando HTTPS:

```
https://localhost:5001/swagger
```

### 2. Teste os Endpoints

No Swagger UI, você pode testar todos os endpoints da API. Para cada endpoint, clique em **Try it out** e depois em **Execute** para realizar a requisição e visualizar a resposta.

### Exemplos de Requisições:

- **Criar um produto (POST /api/products)**

  Corpo da requisição:
  ```json
  {
    "Name": "Produto Teste",
    "Price": 49.99,
    "StockQuantity": 20
  }
  ```

- **Obter a lista de produtos (GET /api/products)**

- **Atualizar um produto (PUT /api/products/{id})**

  Corpo da requisição:
  ```json
  {
    "ProductID": 1,
    "Name": "Produto Atualizado",
    "Price": 39.99,
    "StockQuantity": 100
  }
  ```

- **Deletar um produto (DELETE /api/products/{id})**

## Considerações Finais

- A API foi desenvolvida utilizando boas práticas de arquitetura, com a separação de camadas entre Models, Repositories e Controllers.
- A validação de entrada foi implementada para garantir que os dados dos produtos sejam válidos.
- O Swagger foi integrado para fornecer uma documentação interativa e facilitar os testes dos endpoints.

## Contribuindo

1. Faça o fork do repositório.
2. Crie uma branch para a sua feature (`git checkout -b feature-nome`).
3. Faça commit das suas alterações (`git commit -am 'Adicionando nova feature'`).
4. Faça o push para a branch (`git push origin feature-nome`).
5. Abra um pull request.
