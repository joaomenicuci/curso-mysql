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
```
## **CRIAR BANCO DE DADOS**

create database *nome_bd*<br>
default character set utf8<br>
default collate utf8_general_ci;

### EXEMPLO:

`create database cadastro`<br>
`default character set utf8`<br>
`default collate utf8_general_ci;`

## **CRIAR TABELAS DENTRO DO BANDO DE DADOS**

create table *nome_tabela* (<br>
*nome_da_coluna tipo_primitivo config_adicional*,<br>
) default charset = utf8;

### EXEMPLO:

`create table pessoas (`<br>
`id int not null auto_increment,`<br>
`nome varchar(30) not null,`<br>
`nascimento date,`<br>
`sexo enum('M','F'),`<br>
`peso decimal(5,2),`<br>
`altura decimal(3,2),`<br>
`nacionalidade varchar(20) default 'Brasil',`<br>
`primary key (id)`<br>
`) default charset = utf8;`

## **DELETAR BANCO DE DADOS OU TABELAS**

drop database *nome_bd*;<br>
drop table *nome_tabela*;

### EXEMPLO:

`drop database cadastro;`<br>
`drop table pessoas;`

## **ADICIONAR DADOS NA TABELA**

insert into *nome_tabela*<br>
(coluna1, coluna2, ..., colunaN)<br>
values<br>
(dado1, dado2, ..., dadoN)

### EXEMPLO:
`insert into pessoas`<br>
`(nome, nascimento, sexo, peso, altura, nacionalidade)`<br>
`values`<br>
`('Godofredo', '1984-12-25', 'M', '78.5', '1.83', 'Brasil');`

## **ALTERANDO ESTRUTURA**

alter table *nome_tabela*<br>
add column *nome_coluna* *tipo_primitivo* after *nome_coluna*;<br>
drop column *nome_coluna*;<br>
modify column *nome_coluna* *novo_tipo_primitivo*;<br>
change column *nome_coluna* *novo_nome_coluna* *novo_tipo_primitivo*;<br>
rename to *novo_nome_tabela*;

### EXEMPLO

`alter table pessoas`<br>
`add column profissao varchar(10) after nome;`<br>
`drop column profissao;`<br>
`modify column profissao varchar(20);`<br>
`change column profissao prof varchar(20);`<br>
`rename to população;`

## **MANIPULANDO LINHAS**

update *nome_tabela*<br>
set *nome_coluna* = '*novo_valor*'<br>
where *nome_coluna* = '*valor_coluna*'

### EXEMPLO

`update cursos`<br>
`set nome = 'HTML5'`<br>
`where idcurso = '1';`