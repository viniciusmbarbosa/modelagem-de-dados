# Comandos SQL

Comandos usados para modelagem física.

## Criar banco de dados
```sql
CREATE DATABASE exemplo_vinicius CHARACTER SET utf8mb4;

## Entrar no banco de dados para usá-lo
```sql
USE exemplo_vinicius (REVISAR, NÃO FUNCIONOU)

## Criar a tabela de fabricantes
```sql
CREATE TABLE fabricantes(
  id TINYINT NOT NULL PRIMARY KEY AUTO_INCREMENT, 
  nome VARCHAR(45)
 NOT NULL
 );
```sql
 ## Criar a tabela produtos
```sql
 CREATE TABLE produto(
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000)NOT NULL,
    fabricante_id TINYINT NOT NULL
 );
```sql
 ## Alterando a tabela produtos para criar relacionamento a partir da coluna fabricante_id, com a coluna id da tabela fabricantes 
```sql
 ALTER TABLE produto
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
```sql