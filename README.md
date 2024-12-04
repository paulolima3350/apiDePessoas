# API de Cadastro de Pessoas com Mensageria - RabbitMQ

Este projeto é uma API RESTful para cadastro de pessoas, desenvolvida como exemplo de **Arquitetura de Eventos (EDA)**. O objetivo é implementar comunicação assíncrona entre APIs utilizando **RabbitMQ** como servidor de mensageria.

---

## 🚀 Funcionalidades

- **Cadastro de Pessoas**: Endpoint para registrar nome, telefone e e-mail.
- **Mensageria com RabbitMQ**: Envio de mensagens para uma fila ao cadastrar uma pessoa.
- **Envio de E-mails**: Consumo da fila por outra API para envio de e-mails de boas-vindas (em desenvolvimento).
- **Banco de Dados H2**: Banco em memória para armazenamento temporário de dados.
- **Swagger/OpenAPI**: Documentação interativa da API.

---

## ⚙️ Tecnologias Utilizadas

- **Linguagem**: Java
- **Framework**: Spring Boot
- **Mensageria**: RabbitMQ
- **Banco de Dados**: H2 Database
- **Documentação**: Springdoc OpenAPI (Swagger)
- **Gerenciamento de Dependências**: Maven

---



🔧 Configuração
Requisitos
Java 17+
Maven
RabbitMQ (pode ser usado o CloudAMQP para servidores na nuvem)
Configuração do Banco de Dados
O projeto utiliza H2 Database como banco em memória. As configurações padrão estão no arquivo application.properties:

properties
Copiar código
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.h2.console.enabled=true
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
Configuração do RabbitMQ
Defina as credenciais e o host do RabbitMQ no application.properties:

properties
Copiar código
spring.rabbitmq.host=SEU_HOST
spring.rabbitmq.port=5672
spring.rabbitmq.username=SEU_USUARIO
spring.rabbitmq.password=SUA_SENHA


📤 Endpoints
Cadastro de Pessoas
POST /api/pessoas
Request Body
json
Copiar código
{
  "nome": "João Silva",
  "email": "joao.silva@email.com",
  "telefone": "123456789"
}
Response
json
Copiar código
{
  "id": "f47ac10b-58cc-4372-a567-0e02b2c3d479",
  "nome": "João Silva",
  "email": "joao.silva@email.com",
  "telefone": "123456789",
  "dataHoraCadastro": "2024-12-04T14:00:00"
}

🏗️ Próximas Melhorias
Implementar API para leitura da fila e envio de e-mails.
Configurar autenticação e segurança utilizando JWT.
Migrar para um banco de dados relacional em produção (PostgreSQL ou MySQL).
Adicionar testes unitários e de integração.









