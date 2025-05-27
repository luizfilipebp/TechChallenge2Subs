# Sistema de Gerenciamento de Biblioteca

Este projeto é um sistema de gerenciamento de biblioteca composto por múltiplos microsserviços. Ele utiliza Docker
Compose para orquestrar os serviços e facilitar o desenvolvimento e a execução.

## Estrutura do Projeto

O projeto é dividido nos seguintes microsserviços:

- **ms-discovery**: Serviço de descoberta (Eureka Server).
- **ms-emprestimo**: Microsserviço responsável pela gestão de empréstimos.
- **ms-livros**: Microsserviço responsável pela gestão de livros.
- **ms-usuarios**: Microsserviço responsável pela gestão de usuários.

Além disso, cada microsserviço possui seu próprio banco de dados PostgreSQL.

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Configuração

1. Clone este repositório:
   ```bash
   git clone https://github.com/luizfilipebp/TechChallenge2Subs
   cd techchallenge2subs

## Estrutura de Diretórios

O projeto está organizado da seguinte forma:

```
sistema-biblioteca /
├── ms-emprestimo/        # Código do microsserviço de empréstimos
├── ms-livros/            # Código do microsserviço de livros
├── ms-usuarios/          # Código do microsserviço de usuários
├── msdiscovery/          # Código do serviço de descoberta (Eureka)
├── docker-compose.yml    # Arquivo de configuração do Docker Compose
└── README.md
```

# Documentação do projeto

## Tecnologias Utilizadas

- **Java**: Linguagem principal para os microsserviços.
- **Spring Boot**: Framework para desenvolvimento dos microsserviços.
- **PostgreSQL**: Banco de dados relacional para persistência de dados.
- **Eureka Server**: Serviço de descoberta para registro e localização dos microsserviços.
- **Docker**: Para containerização dos serviços.
- **Docker Compose**: Para orquestração dos containers.


1. Inicialize os submódulos: Certifique-se de baixar os submódulos que contêm os microsserviços:
```
git submodule update --init --recursive
```
2. Verifique as portas disponíveis: Certifique-se de que as portas configuradas no docker-compose.yml (8761, 8081, 8082,
   8083, 5432-5434) estão livres no seu sistema.


3. Suba os containers com Docker Compose: Execute o comando abaixo para construir e iniciar os serviços:
```
docker-compose up --build
```
4. Acompanhe os logs: Verifique os logs para garantir que todos os serviços foram iniciados corretamente:
```
docker-compose logs -f
```
5. Acesse os serviços: Cada microsserviço possui sua própria documentação de API gerada automaticamente pelo Swagger.
   Após iniciar os serviços, você pode acessar a documentação nos seguintes endpoints:

- **ms-emprestimo**: [http://localhost:8081/swagger-ui.html](http://localhost:8081/swagger-ui.html)
- **ms-livros**: [http://localhost:8082/swagger-ui.html](http://localhost:8082/swagger-ui.html)
- **ms-usuarios**: [http://localhost:8083/swagger-ui.html](http://localhost:8083/swagger-ui.html)

6. Parar os containers: Para parar e remover os containers, execute:
```  
docker-compose down
```