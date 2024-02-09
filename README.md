# EjerciciosWilfredo
DROP DATABASE DBEjemplo;

CREATE DATABASE DBEjemplo;

USE DBEjemplo;

CREATE TABLE clientes(
id_cliente INT PRIMARY KEY AUTO_INCREMENT,
nombre_cliente VARCHAR(50),
dui_cliente INT(10),
edad_cliente INT,
telefono_cliente INT
);

CREATE TABLE ordenes(
id_orden INT PRIMARY KEY AUTO_INCREMENT,
producto_orden VARCHAR(20),
fecha_pedido DATE,
id_cliente INT,
FOREIGN KEY(id_cliente)
REFERENCES clientes(id_cliente)
);

INSERT INTO clientes VALUES(1,'John Smith', 123456781, 35, 12345678),
(2,'Alice Johnson', 123456782, 28, 98765432),
(3,'Michael Williams', 123456783, 45, 55553423),
(4,'Emily Davis', 123456784, 30, 11112345),
(5,'David Brown', 123456785, 42, 99993456);

INSERT INTO ordenes VALUES(1,'Shirt', '2022-01-15', 1),
(2,'Pants', '2022-01-16', 2),
(3,'Shoes', '2022-01-17', 3),
(4,'Hat', '2022-01-18', 4),
(5,'Socks', '2022-01-19', 5);

SELECT * FROM clientes;
SELECT * FROM ordenes;

/*FUNCIONES DE AGREGADO*/

/*COUNT*/
SELECT COUNT(id_cliente) FROM clientes WHERE edad_cliente >=30;

/*SUM*/
SELECT SUM() FROM

/*LEFT JOIN*/
SELECT ordenes.id_cliente, clientes.nombre_cliente, clientes.dui_cliente
FROM ordenes
RIGHT JOIN clientes
ON ordenes.id_cliente = clientes.id_cliente
ORDER BY id_orden;
