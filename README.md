# CREATE database policia;

CREATE TABLE Criminoso (
	criminoso_cpf varchar(15) PRIMARY KEY UNIQUE,
    nome varchar(100),
    idade smallint,
    passagens smallint
);

DROP TABLE Criminoso;
DROP TABLE crime;

CREATE TABLE Vitima (
	cpf varchar(15) PRIMARY KEY UNIQUE,
    nome varchar(100),
    idade smallint
);

CREATE TABLE Crime (
    id INT PRIMARY KEY UNIQUE AUTO_INCREMENT,
    tipo VARCHAR(100),
    descricao TEXT,
    FOREIGN KEY (criminoso_cpf)
        REFERENCES Criminoso (cpf),
    FOREIGN KEY (vitima_cpf)
        REFERENCES Vitima (cpf),
    FOREIGN KEY (arma_id)
        REFERENCES Arma (id)
);

CREATE TABLE Arma (
	id int PRIMARY KEY UNIQUE auto_increment,
    armaFogo bool,
    descricao text
);

ALTER TABLE Crime ADD CONSTRAINT fk_criminoso_cpf FOREIGN KEY (cpf) REFERENCES 














