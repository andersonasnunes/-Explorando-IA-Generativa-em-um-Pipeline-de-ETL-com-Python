# 🚀 Santander Dev Week API + IA (OpenAI) + Colab + ngrok

Este projeto demonstra a construção de uma **API REST em Spring Boot**, inspirada na **Santander Dev Week**, integrada com **Inteligência Artificial (OpenAI)** para geração de notícias personalizadas, consumida via **Google Colab**, documentada com **Swagger** e exposta publicamente utilizando **ngrok**.

O objetivo é **educacional e prático**, simulando um cenário real de mercado envolvendo backend, integração com IA e consumo externo de APIs.

---

## 🧩 Visão Geral do Pipeline ETL

### 🔹 Extração (Extract)
- Leitura de **IDs de usuários** a partir de uma planilha .csv
- Consumo da **API da Santander Dev Week 2023**
- Obtenção de dados detalhados de usuários via **requisições HTTP**

### 🔹 Transformação (Transform)
- Tratamento e organização dos dados
- Integração com o **GPT-4 da OpenAI**
- Geração automática de **mensagens personalizadas**
- Aplicação prática de **IA Generativa** em um fluxo de dados

### 🔹 Carregamento (Load)
- Envio das mensagens geradas de volta para a API
- Persistência das informações transformadas
- Conclusão do ciclo ETL

---

## 🛠️ Tecnologias Utilizadas

- ☕ **Java 17**: Backend da API  
- 🗄️ **H2 Database**: Banco de dados em memória para testes  
- 📘 **Swagger**: Documentação e testes da API  
- 🌐 **ngrok**: Exposição da API local para acesso externo  
- 🧠 **OpenAI API**: Geração de conteúdo com Inteligência Artificial  
- 🐍 **Python**: Pipeline ETL e integração de dados
- 📊 **Pandas**: Manipulação, tratamento e transformação de dados no pipeline   
- 📓 **Google Colab**: Execução e testes do pipeline em nuvem

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
---

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

## 📌 Contexto Profissional

Este projeto faz parte do meu portfólio profissional e tem como objetivo demonstrar minhas habilidades em:

Ciência de Dados  
Engenharia de Dados (nível inicial/intermediário)  
Integração de Inteligência Artificial em soluções reais  

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

