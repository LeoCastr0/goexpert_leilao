# Abertura e fechamento automático de Leilão com Go Routines
---
## Descrição

Este é um sistema de leilões desenvolvido em Go. O sistema permite criar leilões, fazer lances e consultar leilões ativos. A aplicação pode ser executada localmente usando Docker e Docker Compose, também é possível executar atalhos através do Makefile.

## Como Executar

### Requisitos

- Makefile
- Docker
- Docker Compose
- Curl

### Passos para Executar Localmente

1. **Clone o repositório:**

   ```sh
   git clone https://github.com/leocastr0/goexpert_leilao.git
   cd goexpert-leilao
   ```

2. **Construir as Imagens**: Na raiz do projeto, execute:

   ```sh
   docker-compose build
   ```

3. **Executar o Docker Compose**: Na raiz do projeto (onde está o arquivo `docker-compose.yml`), execute:

   ```sh
   docker-compose up
   ```

4. **Acesse a aplicação:**

   Acesse a aplicação no endereço `http://localhost:8080`.

### Exemplos de Requisição

- **Para criar leilão:**

   ```sh
   curl -X POST http://localhost:8080/auction \
   -H "Content-Type: application/json" \
   -d '{
        "product_name": "Pet Toy",
        "category": "Pet Supplies",
        "description": "A most popular toy for your pet",
        "condition": 1
       }'
   ```

- **Para buscar leilão por ID:**

   ```sh
   curl -X GET "http://localhost:8080/auction/{auctionId}" \
   -H "Content-Type: application/json"
   ```

- **Para buscar leilões por parâmetros de consulta:**

   ```sh
   curl -X GET "http://localhost:8080/auction?category=Pet%20Supplies&condition=1&status=0" \
   -H "Content-Type: application/json"
   ```
