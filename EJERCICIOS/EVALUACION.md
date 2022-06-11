## Práctica 1.

1. Introducción a base de datos

Objetivo: Identificar el nivel de comprensión de los conceptos de base de datos,
mediante preguntas abiertas.
 
Preguntas:

1. ¿Cuáles son las cinco funciones principales del administrador de bases de datos?
(valor 1.5)

Asegurar el buen funcionamiento de las BD
Retención de información de la BD
Evitar perdida de datos 

Solucionar incidencias y pérdidas de datos
Asegurar la seguridad de los datos

2. Indíque cinco responsabilidades del sistema gestor de bases de datos (valor 1.5)

Instalar, configurar y gestionar bases de datos.
Dar soporte al equipo de desarrollo, seguridad informática y redes.
Definir el esquema del diccionario de datos.
Especificar restricciones de integridad para asegurar los datos.
Garantizar la alta disponibilidad de la base de datos.

3. En una BD al usuario del sistema se le brindarán recursos para realizar diversas
operaciones sobre estos archivos, tales como: (valor 1.5)

4. ¿Qué es un Sistema de Información? (valor 1.5)

Conjunto de elementos orientados al tratamiento y administración de datos e información, organizados y listos para su posterior uso, generados para cubrir la necesidad.

## Práctica 2.

2. Diseño de un modelo relacional

Objetivo: Representar desde un modelo entidad relación un problema


Ejercicio:

Tenemos que diseñar una base de datos sobre proveedores y disponemos de la siguiente
información:

Realiza el modelo entidad relación. (valor 6)

Tenemos esta información sobre una cadena editorial:

● La editorial tiene varias sucursales, con su domicilio, teléfono y un código de
sucursal.

● Cada sucursal tiene varios empleados, de los cuales tendremos su nombre,
apellidos, NIF y teléfono. Un empleado trabaja en una única sucursal.

● En cada sucursal se publican varias revistas, de las que almacenaremos su título,
número de registro, periodicidad y tipo.

● Una revista puede ser publicada por varias sucursales.

● La editorial tiene periodistas (que no trabajan en las sucursales) que pueden
escribir artículos para varias revistas. Almacenaremos los mismos datos que para
los empleados, añadiendo su especialidad.

● También es necesario guardar las secciones fijas que tiene cada revista, que
constan de un título y una extensión.

● Para cada revista, almacenaremos información de cada ejemplar, que incluirá la
fecha, número de páginas y el número de ejemplares vendidos.

![image](https://user-images.githubusercontent.com/104279705/170845534-1754836f-613a-44fd-926b-6651c15b8b8b.png)




 CREATE DATABASE editorial;
 USE editorial;
 
 CREATE TABLE revista (
num_regis INT  UNSIGNED  PRIMARY KEY,
tipo VARCHAR(100) NOT NULL,
titulo_rev VARCHAR(100) NOT NULL,
periodicidad INT UNSIGNED
);


CREATE TABLE sucursales (
cod_suc INT  UNSIGNED  PRIMARY KEY,
tel_suc INT  UNSIGNED,
domicilio VARCHAR(100) NOT NULL
);

CREATE TABLE empleados (
NIF_EMP INT  UNSIGNED  PRIMARY KEY,
tel_emp INT  UNSIGNED,
nom_emp VARCHAR(100) NOT NULL,
ape_emp VARCHAR(100) NOT NULL
);

CREATE TABLE ejemplar (
  fecha INT UNSIGNED PRIMARY KEY,
  num_pag INT UNSIGNED NOT NULL,
  num_vent INT UNSIGNED NOT NULL,
  FOREIGN KEY (num_regis2) REFERENCES revista(num_regis)
  );
https://www.db-fiddle.com/f/mXaZpHVDzHmxBbBk8CG5w/5
