# Desafio Validação e Segurança

[![Java](https://img.shields.io/badge/Java-17%2B-orange?style=flat&logo=openjdk)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?style=flat&logo=springboot)](https://spring.io/projects/spring-boot)
[![Spring Security](https://img.shields.io/badge/Spring%20Security-OAuth2-green?style=flat&logo=springsecurity)](https://spring.io/projects/spring-security)
[![JUnit 5](https://img.shields.io/badge/Testing-JUnit%205-red?style=flat&logo=junit5)](https://junit.org/junit5/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📌 Sobre o Projeto

Este projeto é uma solução do desafio de **Validação e Segurança** proposto no curso do professor **Nélio Alves (DevSuperior)**. 

A proposta do desafio segue o modelo TDD (*Test-Driven Development*): a estrutura base foi obtida através de um *fork* contendo apenas as entidades, DTOs, script de carga inicial de dados (`import.sql`) e a suíte completa de testes integrados e unitários.

O objetivo principal foi implementar a lógica das rotas, aplicando **Bean Validation** para validação de dados de entrada e **Spring Security com OAuth2 (JWT)** para autenticação e autorização por perfis de acesso, garantindo que 100% dos testes sejam concluídos com sucesso.

---

## 🛠️ O que foi Implementado

- **Camada de Controladores / Rotas**: Implementação dos endpoints REST para os recursos do sistema.
- **Validação de Dados (Bean Validation)**:
  - Anotações para validações de campos obrigatórios, tamanho, e-mail válido, etc.
  - Custom Validation para regras específicas (como verificação de e-mail duplicado no cadastro/atualização).
  - Tratamento global de exceções de validação (`MethodArgumentNotValidException`).
- **Segurança e Autorização (Spring Security + OAuth2)**:
  - Configuração do servidor de autenticação e autorização via token JWT.
  - Controle de acesso granual aos endpoints com base nas roles dos usuários (ex: `ROLE_CLIENT`, `ROLE_ADMIN`).
  - Criptografia de senhas com `BCryptPasswordEncoder`.

---

## 🧪 Desenvolvimento Orientado a Testes (TDD)

A aplicação foi guiada pela suíte pré-existente de testes automatizados. Os testes cobrem:

1. **Validação de Dados**:
   - Respostas de erro com status `422 Unprocessable Entity` para payload inválido.
   - Retorno correto da lista de erros de validação estruturados no JSON.
2. **Controle de Acesso / Segurança
