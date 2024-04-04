# bancodedados
Aula de Banco de Dados 04_04_24
CREATE TABLE clientes(

CodC int not null,
nome varchar(80) not null,
cpf char(12) not null,
data_nasc date,
sexo char(1),
salario numeric (9,2),
PRIMARY KEY (CodC),
UNIQUE (cpf),
CHECK (sexo in ('M','F')),
CHECK (salario > 0)
  )
  
CREATE TABLE dvd (

CodD int not null,
titulo varchar(40) not null,
genero varchar(15),
duracao time,
situacao varchar(12) default ('Disponível'),
PRIMARY KEY (CodD),
CHECK (situacao in ('Alugada','Disponível'))

)

DROP TABLE dvd

CREATE TABLE locacoes (
CodC int not null,
CodD int not null,
data date,
FOREIGN KEY (CodC) REFERENCES clientes,
FOREIGN KEY (CodD) REFERENCES dvd,
PRIMARY KEY (CodC, CodD)

)

INSERT INTO clientes
VALUES (1,'Ana Moura', 8245738, '1979-10-02', 'F' ,
650.39)

SELECT * FROM clientes

INSERT INTO dvd (codd, titulo, genero, duracao)
VALUES (1, 'Matrix', 'Ficção', '02:30:00')

SELECT * FROM dvd

INSERT INTO locacoes
VALUES (1, 1, '2003-11-11')
  
SELECT*FROM locacoes
