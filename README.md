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
  select nome_da_coluna from nome_da_tabela;

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

  -- Alterar tabela inserindo uma nova coluna ou atributo
  alter table nome_da_tabela add idade int after nome;

  -- Remover tabela
  drop table nome_da_tabela;
```

### **DML**: Linguagem de manipulação de dados `INSERT`, `UPDATE` e `DELETE`

```sql
  -- Para inserir informações(isso irá criar um usuário)
  insert into nome_da_tabela (
    id,
    nome,
    idade
  ) values (
    1,
    'maria',
    50
  );

  -- Para atualizar dados
  update nome_da_tabela set nome = 'Maria Silva' where id = 1;

  -- Para apagar algum.
  delete from nome_da_tabela where id = 1;

  -- Para verificar a existencia de um banco
  if bd_id ('nome_do_bd') is null create database nome_do_bd;

  -- Verificar se tabela ja existe
  id object_id ('clientes', 'U') is not null drop table clientes;

  create table clientes  (
    cod int not null,
    nome varchar(30),
    sobrenome varchar(50),
    cpf int not null
  );

  -- constraint = restrição

  -- Para adicionar uma chave primaria
  alter table clientes add constraint pk_clientes primary key (cod);

  -- Para adicionar uma ou mais chaves únicas
  alter table clientes add constraint unique_clientes_cpf unique (cpf);

  -- Chave estrangeira
  create table pedidos (
    cod_ped int not null,
    cod_cli varchar(30),
    nome_prod varchar(50),
    qtd int not null
  );

  -- Adicionar chave estrangeira
  alter table pedidos add constraint fk_cod_cli foreign key (cod_cli) references clientes(cod);

  -- check constraint
  create table funcionario (
    cod_func int not null,
    nome varchar(30),
    salario money not null
  );

  -- aplicando check constraint
  alter table funcionario add constraint chk_funcionario_salario check (salario > 0);
```