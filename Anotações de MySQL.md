# **ANOTAÇÕES DE MY SQL**

## **TIPOS DE COMANDOS DE SQL**

### DDL = Data Definition Language
```
create database
create table
alter table
drop table
```
### DML = Data Manipulation Language 
```
insert into
update
delete
truncate
```
## **CRIAR BANCO DE DADOS**

create database *nome_db*<br>
default character set utf8<br>
default collate utf8_general_ci;

### EXEMPLO:
```
create database cadastro
default character set utf8
default collate utf8_general_ci;
```
## **CRIAR TABELAS DENTRO DO BANDO DE DADOS**

create table *nome_tabela* (<br>
*nome_da_coluna* *tipo_primitivo* *config_adicional*,<br>
) default charset = utf8;

### EXEMPLO:
```
create table pessoas (
id int not null auto_increment,
nome varchar(30) not null,
nascimento date,
sexo enum('M','F'),
peso decimal(5,2),
altura decimal(3,2),
nacionalidade varchar(20) default 'Brasil',
primary key (id)
) default charset = utf8;
```
## **DELETAR BANCO DE DADOS, TABELAS OU LINHAS**

drop database *nome_bd*;<br>
drop table *nome_tabela*;<br>
<br>
delete from *nome_tabela*<br>
where idcurso = '*numero_idcursos*'<br>
<br>
truncate table *nome_tabela*

### EXEMPLO:
```
drop database cadastro;
drop table pessoas;

delete from cursos
where idcurso = '8';
truncate table cursos;
```
## **ADICIONAR DADOS NA TABELA**

insert into *nome_tabela*<br>
(coluna1, coluna2, ..., colunaN)<br>
values<br>
(dado1, dado2, ..., dadoN)

### EXEMPLO:
```
insert into pessoas
(nome, nascimento, sexo, peso, altura, nacionalidade)
values
('Godofredo', '1984-12-25', 'M', '78.5', '1.83', 'Brasil');
```
## **ALTERANDO ESTRUTURA**

alter table *nome_tabela*<br>
add column *nome_coluna* *tipo_primitivo* after *nome_coluna*;<br>
drop column *nome_coluna*;<br>
modify column *nome_coluna* *novo_tipo_primitivo*;<br>
change column *nome_coluna* *novo_nome_coluna* *novo_tipo_primitivo*;<br>
rename to *novo_nome_tabela*;

### EXEMPLO
```
alter table pessoas
add column profissao varchar(10) after nome;
drop column profissao;
modify column profissao varchar(20);
change column profissao prof varchar(20);
rename to população;
```
## **MANIPULANDO LINHAS**

update *nome_tabela*<br>
set *nome_coluna* = '*novo_valor*'<br>
where *nome_coluna* = '*valor_coluna*'

### EXEMPLO
```
update cursos
set nome = 'HTML5'
where idcurso = '1';
```
## **COMANDO SELECT**

select * from *nome_tabela*<br>
select *nome_coluna* from *nome_tabela*<br>
where *nome_coluna* = '*valor_coluna*'<br>
order by *nome_coluna*

### EXEMPLO
```
select * fom cursos
where ano = '2016'
order by nome
```