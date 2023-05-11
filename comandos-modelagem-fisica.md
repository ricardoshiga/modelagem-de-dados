# Comandos SQL

Comandos usandos para a modelagem física.

## Criar banco de dados

CREATE DATABASE exemplo_ricardo CHARACTER SET utf8mb4;

## Entrar no banco de dados para utiliza-lo

USE exemplo_ricardo; (*DATABASE revisar, não funcionou)

## Criar a tabela de fabricantes

CREATE TABLE fabricantes(
    id TINYINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);

## Criar a taebla produtos

CREATE TABLE produtos(
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id TINYINT

    );


 ## Alterando a tabela produtos para criar relacionamento a partir da coluna fabricante_id, com a colunaid da tabela fabricantes

 ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
