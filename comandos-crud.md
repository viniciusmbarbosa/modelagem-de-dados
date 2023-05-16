# Comandos SQL para operações de dados (CRUD)

## Resumo

C: CREATE (criar dados usandoo o comando INSERT)
R: READ (ler dados usando o comando SELECT)
U: UPDATE (atualizar dados usando o comando DELETE)
D: DELETE (excluir dados usando o comando DELETE)

## INSERT 

````sql
INSERT INTO fabricantes (nome)VALUES('Microsoft');
INSERT INTO fabricantes (nome)VALUES('Asus');
INSERT INTO fabricantes (nome)VALUES('Dell');

INSERT INTO fabricantes (nome)
VALUES('apple'), ('LG'), ('Samsung'), ('Brastemp');
```

### Tabela produtos

SELECT descricao, nome FROM produtos;

/* Exercicio trazer o nome dos produtos apenas da Apple
   Dica: use o comando WHER para indicar a condicão  */

````sql
INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('Ultrabook', 'Laptop de útima geração com processador Inter core i9 e memória de 16 gb ram.', 3);

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('Tablet Android', 'Tabelet com a versão 13 do sistema Android, com tela de 10 polegadas e 64 GB de armazenamento.', 3);

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('iPhone 13 Pro Max', 'Alta durabilidade, processador XYZ 14, 128 GB de armazenamento, 6 GB de RAM e caro pra caramba.', 1);

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('Geladeira', 'Refrigerador frost-free com acesso à Internet e bal bla bal', 4)

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('xbox','Vídeo-game de última geração.', 1 )

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES('IPad Mini', 'Tablet Apple com tela retina de 4k', 1)

INSERT INTO produto (nome, descricao, fabricante_id)
VALUES ('Ultrabook', 'Equipamento com processador AMD Ryzen, 12 GB de RAM', 2);
````

### Ler dados da tabela Produto

```sql
SELECT * FROM produtos;

SELECT NOME FROM produtos;

SELECT nome FROM produto WHERE fabricante_id = 1;

/* símbolo de diferente ! = OU <> */
SELECT nome FROM produto WHERE fabricante_id != 1;

SELECT nome FROM produto WHERE fabricante_id <> 1;



-- OPERADOR OU: OR
SELECT nome FROM produto
WHERE fabricante_id = 2 OR fabricante_id = 3

-- ORDENANDO POR ORDEM CRESCENTE
SELECT nome, descricao FROM produto ORDER BY nome;

-- ORFERNANDO POR ORDEM DECRESCENTE (DESC)
SELECT nome, descricao FROM produtos ORDER BY nome DESC;

SELECT COUNT(id) AS Quantidade FROM produto;