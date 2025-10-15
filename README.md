# Desafio Docker Compose - Gerador de Saudações
Este repositório contém a solução para um desafio acadêmico focado em aplicar conceitos fundamentais de DevOps utilizando Docker e Docker Compose. O objetivo foi containerizar uma aplicação de microsserviços e orquestrar sua execução de forma coesa e automatizada.

### 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [✨ Demonstração](#-demonstração)
- [🔧 Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [▶️ Como Executar o Projeto](#️-como-executar-o-projeto)
- [📂 Estrutura do Projeto](#-estrutura-do-projeto)
- [🧠 Aprendizados](#-aprendizados)
- [👨‍💻 Autor](#-autor)

  ---
  
**Sobre o Projeto**

A aplicação "Gerador de Saudações" é composta por três serviços independentes:

**Frontend (site-gerador-saudacoes)**: Uma página web simples em HTML e CSS, servida por um contêiner Nginx, que consome os outros dois microsserviços.

**Microsserviço de Pessoas (ms-pessoas-aleatorias)**: Uma API em Python que retorna um nome de pessoa aleatório.

**Microsserviço de Saudações (ms-saudacoes-aleatorias)**: Uma API em Go que retorna uma saudação aleatória.

O desafio consistiu em criar um ```Dockerfile``` para cada um desses serviços, fazer o build das imagens, publicá-las no Docker Hub e, finalmente, criar um arquivo ```docker-compose.yaml``` para orquestrar a subida e a comunicação entre os três contêineres.

---

**✨ Demonstração**
Abaixo, a aplicação em pleno funcionamento, com o frontend se comunicando com os dois microsserviços de backend para gerar uma saudação completa.

captura-de-tela.png

---

**🔧 Tecnologias Utilizadas**

- Orquestração e Containerização:
  - Docker
  - Docker Compose

- Frontend:
  - HTML5
  - CSS3
  - Nginx (como servidor web)

- Backend - Microsserviço de Pessoas:
  - Python

- Backend - Microsserviço de Saudações:
  - Go (Golang)

---

**▶️ Como Executar o Projeto**
Para executar este projeto em sua máquina local, siga os passos abaixo.

Pré-requisitos
Git instalado.

Docker e Docker Compose instalados e em execução.

Passos para Execução
Clone o repositório:
```
Bash

git clone https://github.com/ThiagoHerc/desafio-docker-compose.git
```
Navegue até o diretório do projeto:
```
Bash

cd desafio-docker-compose
```
Inicie a aplicação com Docker Compose:
O comando abaixo irá baixar as imagens prontas do Docker Hub e iniciar os três contêineres em segundo plano (-d).
```
Bash

docker-compose up -d
```
Se preferir construir as imagens localmente a partir dos Dockerfiles, use o comando ```docker-compose up --build -d.```

Acesse a aplicação:
Abra seu navegador e acesse http://localhost.
A página do Gerador de Saudações deve aparecer e estar funcionando!

Para parar a aplicação:
```
Bash

docker-compose down
```
---

**📂 Estrutura do Projeto**
```
desafio-docker-compose/
├── site-gerador-saudacoes/
│   ├── Dockerfile
│   └── ... (código fonte do site)
│
|
├── ms-pessoas-aleatorias/
│   ├── Dockerfile
│   └── ... (código fonte em Python)
│
|
├── ms-saudacoes-aleatorias/
│   ├── Dockerfile
│   └── ... (código fonte em Go)
│
|
├── docker-compose.yaml       # Arquivo de orquestração
├── README.md                 # Este arquivo
└── captura-de-tela.png       # Screenshot da aplicação
```
---

**🧠 Aprendizados**

Este projeto foi uma excelente oportunidade para solidificar conhecimentos práticos em:

**Criação de Dockerfiles**: Escrever Dockerfiles otimizados para diferentes linguagens e ambientes (Nginx, Python, Go).

**Multi-Stage Builds**: Utilizar a técnica de múltiplos estágios para reduzir drasticamente o tamanho das imagens finais e aumentar a segurança, separando o ambiente de build do ambiente de execução.

**Publicação de Imagens**: Gerenciar um repositório no Docker Hub, versionar imagens com tags e publicá-las para uso remoto.

**Orquestração com Docker Compose**: Definir, configurar e gerenciar uma aplicação multi-contêiner, incluindo a configuração de redes e dependências entre serviços.

**Resolução de Problemas**: Diagnosticar e resolver problemas comuns do ecossistema Docker, como conflitos de porta (address already in use), erros de permissão no daemon do Docker e problemas de autenticação com registros remotos.

---

**👨‍💻 Autor**

Feito com persistência e muito café por **Thiago Herculano**.
