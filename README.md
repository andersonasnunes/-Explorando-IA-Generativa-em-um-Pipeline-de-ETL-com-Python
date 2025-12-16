# 🚀 Santander Dev Week API + IA (OpenAI) + Colab + ngrok

Este projeto demonstra a construção de uma **API REST em Spring Boot**, inspirada na **Santander Dev Week**, integrada com **Inteligência Artificial (OpenAI)** para geração de notícias personalizadas, consumida via **Google Colab**, documentada com **Swagger** e exposta publicamente utilizando **ngrok**.

O objetivo é **educacional e prático**, simulando um cenário real de mercado envolvendo backend, integração com IA e consumo externo de APIs.

---

## 🧩 Tecnologias Utilizadas

- ☕ Java 17  
- 🌱 Spring Boot  
- 🗄️ H2 Database (em memória)  
- 📘 Swagger / OpenAPI  
- 🌐 ngrok  
- 🧠 OpenAI API  
- 🐍 Python  
- 📓 Google Colab  
- 📦 Maven  

---

## 🏗️ Arquitetura do Projeto

```text
Google Colab (Python + OpenAI)
        |
        |  HTTP (ngrok)
        v
ngrok (URL pública)
        |
        v
Spring Boot API (localhost:8080)
        |
        v
Banco H2 (em memória)
```
---

## 🗄️ Banco de Dados – H2

O projeto utiliza o **H2 Database**, ideal para desenvolvimento, testes e fins didáticos.

### Vantagens:
- Não requer instalação
- Banco em memória
- Inicialização rápida
- Fácil visualização

### Console H2:
http://localhost:8080/h2-console


Configuração padrão:
- JDBC URL: `jdbc:h2:mem:testdb`
- Usuário: `sa`
- Senha: *(vazia)*

---

## 📌 API Santander (Modelo)

A API segue o modelo proposto pela **Santander Dev Week**, com a entidade principal `User`, composta por:

- Conta bancária (`account`)
- Cartão (`card`)
- Funcionalidades (`features`)
- Notícias personalizadas (`news`)

### Exemplo de estrutura do usuário:
```json
{
  "id": 1,
  "name": "Anderson Nunes",
  "account": {
    "number": "98765-4",
    "agency": "0001",
    "balance": 2500.00,
    "limit": 1500.00
  },
  "card": {
    "number": "5412 9876 4321 0001",
    "limit": 3000.00
  },
  "features": [],
  "news": []
}
```
## 📘 Swagger (Documentação da API)

O Swagger é utilizado para documentar e testar os endpoints da API.

### Acesso local:
[http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)

### Funcionalidades:
- **Criação de usuários**: `POST /users`
- **Consulta de usuários**: `GET /users/{id}`
- **Validação da estrutura dos dados**.

---

## 🌐 Exposição da API com ngrok

Como o **Google Colab** não consegue acessar `localhost`, o **ngrok** foi utilizado para expor a API local de forma pública.

### Comando utilizado:
```bash
ngrok http 8080
```

### Exemplo de URL gerada
https://xxxxxx.ngrok-free.dev


Essa URL é usada no **Google Colab** para consumir a API remotamente.

---

## 🧠 Integração com OpenAI (IA)

A **OpenAI API** é utilizada para gerar **notícias personalizadas** para cada usuário, simulando campanhas de marketing bancário inteligentes.

### Funcionalidades
- Geração automática de mensagens
- Conteúdo curto e personalizado
- Associação dinâmica das mensagens a cada usuário

### Modelo utilizado
gpt-4o-mini


### Boas práticas adotadas
- Uso de variável de ambiente (`OPENAI_API_KEY`)
- Reutilização do client
- Limite de tokens para controle de custos

---

## 📓 Google Colab (Consumo da API)

O **Google Colab** foi utilizado para consumir a API remotamente e integrar com a IA.

### Principais usos
- Leitura de usuários via CSV
- Requisições HTTP (`GET /users/{id}`)
- Geração de notícias com OpenAI
- Atualização do objeto do usuário

### Principais bibliotecas
```python
import pandas as pd
import requests
from openai import OpenAI

```

## ❗ Problemas Comuns Resolvidos

- ❌ **Retorno `[]`** → uso incorreto de `localhost` no Google Colab  
- ❌ **Erro 404** → usuário não existente  
- ❌ **Erro OpenAI v1** → migração para a nova versão da API  
- ❌ **Erro ngrok** → falta de configuração do authtoken  

Todos esses cenários fazem parte do aprendizado proposto pelo projeto.

---

## 🎯 Objetivo Educacional

Este projeto foi desenvolvido para:

- Aprender **Spring Boot** e **APIs REST**
- Trabalhar com **banco de dados em memória**
- Integrar **Inteligência Artificial**
- Consumir **APIs remotamente**
- Simular um **cenário real de mercado**
- Servir como **projeto de portfólio**

---

## 🧑‍💻 Autor

**Anderson Nunes**  
Desenvolvedor | Educador | Engenheiro de Software

---

## ⭐ Considerações Finais

Este projeto une **backend moderno**, **inteligência artificial** e **integração remota**, sendo uma excelente base para evoluções futuras como:

- PostgreSQL
- Docker
- Deploy em nuvem
- Autenticação JWT


