# Comandos SQL para operações de dados (CRUD)




## Resumo




C: CREATE (criar dados usando o comando INSERT)

R: READ (ler os dados usando o comando SELECT)

U: UPDATE (atualizar os dados usando o comando UPDATE)

D: DELETE (excluir os dados usando o comando DELETE)




## INSERT

### Tabela fabricantes




```sql

INSERT INTO fabricantes (nome) VALUES('Microsoft');

INSERT INTO fabricantes (nome) VALUES('Asus');

INSERT INTO fabricantes (nome) VALUES('Dell');




INSERT INTO fabricantes (nome)

VALUES('Apple'), ('LG'), ('Samsung'), ('Brastemp');

```




### Tabela produto

```sql

INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Ultrabook', 'Laptop de última geração com processador Intel Core i9 e memória de 16 GB RAM.', 3)

INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Tablet Android', 'Tablet com a versão 13 do sistema Android, com tela de 10 polegadas e 64 GB de armazenamento.', 6)




INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Iphone 13 Pro Max', 'Alta durabilidade, processador XYZ 14, 128 GB de armazenamento, 6 GB de RAM e caro pra caramba.', 4)




INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Geladeira', 'Refrigerador frost-free com acesso à internet e bla bla bla.', 7)




INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Xbox 123', 'Vídeo-game de última geração.', 1)




INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('iPad Mini', 'Tablet Apple com tela retina de 4k.', 4)

INSERT INTO produto (nome, descricao, fabricante_id)

VALUES('Ultrabook', 'Equipamento com processador AMD Ryzen, 12 GB de RAM.', 2)

```

### Ler dados da tabela Produtos

```sql

SELECT * FROM produto;




SELECT nome FROM produto;




SELECT nome, descricao FROM produto;




/* Trazer o nome dos produto apenas da Apple. WHERE (ONDE) indica a condição */

SELECT nome FROM produto WHERE fabricante_id = 4;




/*OPERADOR DIFERENTE: != ou <> */

SELECT nome FROM produto WHERE fabricante_id != 4;

SELECT nome FROM produto WHERE fabricante_id <> 4;




/* OPERADOR OU: OR */

SELECT nome, descricao FROM produto

WHERE fabricante_id = 2 OR fabricante_id = 3;




/* ORDEM CRESCENTE (ASC - padrão) */

SELECT nome, descricao FROM produto ORDER BY nome;

/* ORDEM DECRESCENTE (DESC) */

SELECT nome, descricao FROM produto ORDER BY nome DESC;

/* COUNT(campo especial) é uma função de contagem de registros */

SELECT COUNT(id) FROM produto;




/* Usando AS para definir um apelido para a coluna de resultados */

SELECT COUNT(id) AS Quantidade FROM produto;

```




## UPDATE (SEMPRE COM WHERE!!)

```sql

UPDATE fabricantes SET nome = 'Asus do Brasil' WHERE id = 2;

```

<!-- 1) Na tabela de produtos, atualize o produto Gelarideira mudando o fabricante de Brastemp para samsung.

2) Na tabela de produtos, referente ao produto Xbox 123, mude o nome para "Xbox One" e a descrição para "Novo lançamento com parcelamento em 256x.-->

````sql
UPDATE produto SET fabricantes_id = 6 WHERE id = 4;

UPDATE produto SET nome = 'Xbox One', descricao = 'Novo lançamento com parcelamento em 256x.' WHERE id = 5;

```
DELETE FROM produto WHERE id = 3;

-- ERRO (não da para apagar há produtos deste fabricante)
DELETE FROM fabricantes WHERE id = 1;

