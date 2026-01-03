# 🎮 GameList API

[![Java](https://img.shields.io/badge/Java-17%2B-orange?style=for-the-badge&logo=openjdk)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-brightgreen?style=for-the-badge&logo=springboot)](https://spring.io/projects/spring-boot)
[![Hibernate](https://img.shields.io/badge/Hibernate-ORM-59666C?style=for-the-badge&logo=hibernate)](https://hibernate.org/)

API REST para gerenciamento de catálogos de jogos, permitindo a consulta detalhada de títulos e a organização personalizada através de listas com suporte a reordenamento (logica de drag-and-drop no backend).

---

## 📝 Sobre o Projeto
Este projeto demonstra o domínio em Java com Spring Boot, focando na separação de responsabilidades e na performance de consultas ao banco de dados, utilizando DTOs para tráfego eficiente de dados e JPQL para consultas customizadas.



## 🛠️ Tecnologias e Conceitos
- **Spring Boot 3**: Framework principal.
- **Spring Data JPA & Hibernate**: Persistência e consultas ao banco.
- **H2 Database**: Banco de dados em memória para testes e agilidade.
- **DTO (Data Transfer Object)**: Padrão para otimizar a resposta da API.
- **Domain Model**: Entidades `Game`, `GameList` e a tabela associativa `Belonging`.

---

## 🛣️ Endpoints da API

### 🕹️ Jogos (`/games`)
| Método | Endpoint | Descrição | Retorno |
| :--- | :--- | :--- | :--- |
| `GET` | `/games` | Lista todos os jogos cadastrados. | `List<GameMinDTO>` |
| `GET` | `/games/{id}` | Busca os detalhes completos de um jogo. | `GameDTO` |

### 📂 Listas de Jogos (`/lists`)
| Método | Endpoint | Descrição | Retorno |
| :--- | :--- | :--- | :--- |
| `GET` | `/lists` | Lista todas as categorias/listas. | `List<GamelistDTO>` |
| `GET` | `/lists/{listId}/games` | Retorna todos os jogos de uma lista específica. | `List<GameMinDTO>` |
| `POST` | `/lists/{listId}/replacement` | Altera a posição de um jogo dentro da lista. | `void` |

---

## 🏗️ Estrutura de Camadas
A API segue o padrão de camadas:
1. **Controller**: Camada de recursos REST.
2. **Service**: Camada de lógica de negócio.
3. **Repository**: Camada de acesso a dados.

---

## 🚀 Como Executar

### 📋 Pré-requisitos
* **Java 17** ou superior.
* **Maven 3.8+**.
* Uma IDE (IntelliJ, Eclipse, VS Code).

### 🛠️ Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/Giovani-Gomes/GameList_API.git](https://github.com/Giovani-Gomes/GameList_API.git)

Acesse a pasta do projeto:

### 🗄️ Configuração do Banco de Dados (H2)

O projeto utiliza o banco de dados **H2 em memória** para agilizar o desenvolvimento e facilitar os testes iniciais sem a necessidade de instalar um banco externo.

* **Console H2:** [http://localhost:8080/h2-console](http://localhost:8080/h2-console)
* **JDBC URL:** `jdbc:h2:mem:testdb`
* **Usuário:** `sa`
* **Senha:** *(manter em branco)*
