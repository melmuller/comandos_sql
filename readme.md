# Comandos de banco de dados

### Criar database
* Local para criar as tabelas do sistema
```
create database NOME_DATABASE
```
### Executar o comando 
```
Ctrl + Enter
```
### Selecionar database
```
use NOME_DATABASE
```
## Projeto site Ecommerce
* Tabela de usuários
* Tabela de produtos
* Tabela de carrinho de compras

### Criar tabela de usuários
```
create table usuarios(
    id int not null auto_autoincrement, nome varchar(120) not null, email varchar(120) not null, senha varchar(120) not null, primary key(id)
);
```
* id: identificador de registro
* not null: campo obrigatório, não pode ser nulo
* auto_autoincrement: soma +1 no último registro de id
* varchar(120): Campo de texto com 120 caracteres

### Criar tabela de produtos
```
create table produtos (
    id int not null auto_increment, modelo varchar(120), nome varchar (120) not null, valor float not null, primary key (id)
);
```

### Criar tabela de carrinho
```
create table carrinho(
    id int not null auto_increment, id_usuario int not null, id_produto not null, primary key (id), foreign key(id_usuario) references usuarios(id), foreign key (id_produto) references produtos(id)
);
```
* foreign key: chave estrangeira que recebe a referencia de outra tabela
* references: atributo para definir a tabela e o campo estrangeiro

### Inserir usuarios
```
insert into usuarios(nome, email, senha) values('Lucca Holanda', 'teste@teste.com', 'secret');
```

### Inserir produto
```
insert into produtos(modelo, nome, valor) values('nike', 'camiseta', 129.90);
```

### Inserir carrinho 
```
insert into carrinho(id_usuario, id_produto) values(43, 234);
insert into carrinho(id_usuario, id_produto) values(43, 212);
```

# Comandos de listagem

### Listar todas as colunas usuarios
```
select * from usuarios;
```

### Listar os nomes dos usuarios
```
select nome from usuarios;
```

### Listar nomes e email dos usuários
```
select nome, email from usuario;
```

### Listar usuários pelo id
```
select * from usuarios where id = ***;
```

### Verificar produtos no carrinho pelo id do usuario
```
select nome
from produtos p, carrinho c
where id_usuario = ***;
```