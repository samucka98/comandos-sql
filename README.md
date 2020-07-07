# Comandos SQL

*Este é um breve resumo dos comandos que são mais usados para manipular bancos de dados relacionais SQL* 

## Principais comandos

* **CREATE DATABASE** - Cria um novo banco de dados
* **ALTER DATABASE** - Modifica um banco de dados
* **SELECT** - Obter dados de um banco de dados
* **UPDATE** - Atualiza dados em um banco de dados
* **DELETE** - Exclui dados de um banco de dados
* **INSERT INTO** - Insere novos dados em um banco de dados
* **CREATE TABLE** - Cria uma nova tabela
* **ALTER TABLE** - Modifica uma tabela
* **DROP TABLE** - Exclui uma tabela
* **CREATE INDEX** - Cria um índice (chave de pesquisa)
* **DROP INDEX** - Exclui um índice


### **DQL**: Linguagem de consulta de dados `SELECT`

```sql
  -- Seleção simples de uma coluna em uma tabela
  select nome_da_coluna from nomedatabela;

  -- Seleção de multiplas colunas em uma tabela
  select nome_da_coluna1, nome_da_coluna2, ... from nome_da_tabela;

  -- Seleção de todas as colunas de uma tabela
  select * from nome_da_tabela;
```

### **DDL**: Linguagem de definição de dados `CREATE`, `ALTER` e `DROP`

```sql
  -- Criar um novo banco de dados
  create database nome_do_banco;

  -- É importante depois de criado o banco de dados usar este com o comando abaixo
  use nome_do_banco;

  -- Remover(excluir) um banco de dados
  drop database nome_do_banco;

  -- Criar tabela
  create table nome_da_tabela(
    -- aqui dentro ficam os atributos
    id int,
    nome varchar(255)
  )

  -- Alterar tabela inserindo uma nova coluna
  alter table nome_da_tabela add idade int after nome; 
```

