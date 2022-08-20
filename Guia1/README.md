REQUERIMIENTOS:

 -Docker
 
 -nodeJs

COMANDOS PARA MONTAR LA BASE DE DATOS MYSQL EN DOCKER:

docker pull mysql

docker run -d -p 3306:3306 --name mysql-db -e MYSQL_ROOT_PASSWORD=secret mysql --lower_case_table_names=1

docker exec -it mysql-db mysql -p

password: secret

CREACIÓN DE LA BASE DE DATOS CON LA TABLA USER:

create database gestion;

use gestion;

create table user(
id mediumint not null AUTO_INCREMENT, 
firstName VARCHAR(32) NOT NULL, 
lastName VARCHAR(32) NOT NULL, 
document VARCHAR(16) NOT NULL, 
address VARCHAR(64) NOT NULL, 
phone INT(10) DEFAULT NULL, 
email VARCHAR(32) DEFAULT NULL, primary key(id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
ALTER TABLE user ADD UNIQUE document(document);

VOLCADO DE DATOS TABLA USER:

INSERT INTO user (firstName, lastName, document, address, phone, email) VALUES ("Kevin","Vargas","1024561584", "Calle falsa 123", 100000000, "kevin@email.com");
INSERT INTO user (firstName, lastName, document, address, phone, email) VALUES ("Fabian","Vargas","1024561583", "Calle falsa 456", 200000000, "fabian@email.com");
INSERT INTO user (firstName, lastName, document, address, phone, email) VALUES ("Diego","Vargas","1000000000", "Calle falsa 789", 300000000, "diego@email.com");
INSERT INTO user (firstName, lastName, document, address, phone, email) VALUES ("Carlos","Vargas","2000000000", "Calle falsa 123", 400000000, "carlos@email.com");
INSERT INTO user (firstName, lastName, document, address, phone, email) VALUES ("Robert","Osorio","7000000000", "Calle falsa 123", 400000000, "carlos@email.com");

select * from user;

PASOS PARA EJECUTAR EL PROYECTO:

npm init -y -> Para iniciar nuestro proyecto con node

npm install mysql2 -> Para conectarnos a la base de datos.

npm consulta.js -> Para ejecutar el proyecto

INSTALACIÓN DE EXPRESS PARA CREAR UN SERVIDOR:

npm install express -> Para instalar el modulo express

INSTALACIÓN DE UN MOTOR DE PLANTILLAS PARA HACER RENDERS DINAMICOS:

npm install pug -> Para instalar el motor de plantillas pug

POR ULTIMO:

node consulta.js -> Para ejecutar nuestro servidor

Visitar http://localhost:3000
