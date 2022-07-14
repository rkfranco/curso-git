CREATE database policia;

CREATE TABLE Criminoso (
    criminoso_cpf varchar(15) PRIMARY KEY UNIQUE, 
    nome varchar(100), 
    idade smallint, 
    passagens smallint 
);

INSERT INTO Criminoso 
VALUES ('123.321.456-58', 'Ronald McDonald', 120, 78),
       ('123.321.456-59', 'Ronald McDonald 2', 100, 80), 
       ('123.321.456-60', 'Ronald McDonald 3', 84, 95);

CREATE TABLE Vitima (
    vitima_cpf varchar(15) PRIMARY KEY UNIQUE, 
    nome varchar(100), 
    idade smallint 
);

INSERT INTO Vitima
VALUES ('111.111.111-01', 'Vitima da Silva', 80),
       ('111.111.111-02', 'Vitima da Silva 2', 50),
       ('111.111.111-03', 'Vitima da Silva 3', 20);

CREATE TABLE Arma (
    arma_id int PRIMARY KEY UNIQUE auto_increment, 
    armaFogo bool, 
    descricao text 
);

INSERT INTO Arma 
VALUES ('1', true, 'Revolver'),
       ('2', false, 'Tridente');

CREATE TABLE Crime (
    crime_id int PRIMARY KEY UNIQUE AUTO_INCREMENT, 
    tipo varchar(100), 
    descricao text,
    criminoso_cpf varchar(15),
    vitima_cpf varchar(15),
    arma_id int, 
    FOREIGN KEY (criminoso_cpf) REFERENCES Criminoso(criminoso_cpf),
    FOREIGN KEY (vitima_cpf) REFERENCES Vitima(vitima_cpf),
    FOREIGN KEY (arma_id) REFERENCES Arma(arma_id)
);

INSERT INTO Crime
VALUES 
(null, 'Assalto', 'Ocorreu um assalto', '123.321.456-58', '111.111.111-01', 2),
(null, 'Homicidio', 'Assasinato na praça dos palmitos', '123.321.456-59', '111.111.111-02', 1),
(null, 'McDonald', 'Ocorreu um assalto', '123.321.456-60', '111.111.111-03', 1);

SELECT * FROM Crime;







