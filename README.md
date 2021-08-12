# BikeMarket usando o POSTGRES
Criação e consultas de vendas no Postgres

# Iniciando o Postgres
sudo service postgresql-11 start

# Entrando no postgres
Sudo -u postgres psql

# Criando uma base de dados
Create database nomedabase;

# Verificar quais são as bases existentes
/list

# Acessando o banco de dados(no nosso caso será o banco de dados “ed”)
\c ed

# Acessando scrips já feitos
\i /home/Cloudera/Downloads/1.CreateTable.sql

# Adicionando informações nas tabelas
INSERT INTO Relacional.clientes(cliente, estado, sexo, status) VALUES('Willian Nakasato', 'SP', 'M', 'Platinum');
INSERT INTO Relacional.vendedores(nome) VALUES ('Tobias Furtado');
INSERT INTO Relacional.produtos(produto, preco) VALUES ('Notebook Apple M1', 9500.00);
INSERT INTO Relacional.vendas(idvendedor, idcliente, data, total) VALUES(1991, 2710, '11/08/2021', 9650.00);

# Exemplos de funções para SQL:
select * from relacional.clientes where cliente = "Willian Nakasato";
select * from relacional.clientes limit 10;
select * from relacional.clientes where status not in ('Platinum');
ed=# select * from relacional.vendas where total > 9000;
ed=# select idvendedor, count(idvendedor) from relacional.vendas group by idvendedor;
ed=# update relacional.clientes set estado = 'TO', status = 'Gold' where cliente = 'Willian Nakasato';
