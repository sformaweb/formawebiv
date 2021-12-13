# `SQL`

SQL é unha linguaxe estándar para almacenar, manipular e recuperar datos en bases de datos.

SQL non é o úneco sistema de bases de datos. MySQL, SQL Server, MS Access, Oracle, Sybase, Informix, Postgres son outros sistemas de bases de datos.
~~Co noso editor SQL en liña, pode editar as instrucións SQL e facer clic nun botón para ver o resultado.~~

## Que é SQL?

SQL é unha linguaxe estándar para acceder e manipular bases de datos.

Exemplo:
```
SELECT * FROM clientes;
```

- SQL significa Structured Query Language
- SQL permite acceder, consultar e manipular bases de datos
- SQL converteuse nun estándar do American National Standards Institute (ANSI) en 1986 e da Organización Internacional de Normalización (ISO) en 1987.

## Que pode facer SQL?

- SQL pode executar consultas contra unha base de datos

- SQL pode recuperar datos dunha base de datos

- SQL pode inserir rexistros nunha base de datos

- SQL pode actualizar rexistros nunha base de datos 
  
- SQL pode eliminar rexistros dunha base de datos 
  
- SQL pode crear novas bases de datos 
  
- SQL pode crear novas táboas nunha base de datos 
  
- SQL pode crear procedementos almacenados nunha base de datos 
  
- SQL pode crear vistas nunha base de datos 
  
- SQL pode establecer permisos en táboas, procedementos e vistas 
  
- SQL é un estándar - PERO... 
   Aínda que SQL é un estándar ANSI/ISO, hai diferentes versións da linguaxe SQL.
   
   Non obstante, para cumprir co estándar ANSI, todos admiten polo menos os comandos principais (como SELECT, UPDATE, DELETE, INSERT, WHERE) dun xeito similar. 
   
   *NOTA: a maioría dos programas de bases de datos SQL, ademais de cumprir co estándar SQL, tamén teñen extensións propietarias propias.*

## Usando SQL no teu sitio web

Para crear un sitio web que mostre datos dunha base de datos, necesitarás: 

- Un programa de base de datos RDBMS(*Relational Database Management System*) (p.ex: MS Access, SQL Server, MySQL) 
- Utilizar unha linguaxe de script do lado do servidor, como PHP ou ASP 
  - Para usar SQL e para xestionarr os datos que queres 
  - Para usar HTML/CSS e proporcionarlle estrutura e estilo visual á páxina 

RDBMS é a base funcional para todos os sistemas de bases de datos modernos como MS SQL Server, IBM DB2, Oracle, MySQL ou Microsoft Access. 

Os datos en RDBMS almacénanse en obxectos de base de datos chamados táboas. Unha táboa, que consta de fileiras e columnas, é unha colección de entradas de datos relacionadas. 



==Exemplo:==

- Mirando a táboa `clientes`:

  `SELECT * FROM clientes;`

Cada táboa divídese en entidades máis pequenas chamadas *campos*. Os campos da táboa ``clientes`` consisten en diferentes columnas cos encabezados: ``clienteID``, ``clienteNome``, ``clienteEmail``, ``clienteDireccion``, ``clienteCidade``, ``clienteCP`` e ``clientePais``. Os datos de cada cliente ocuparán unha fila, e cada campo da columna da táboa manterá a información específica sobre cada rexistro da táboa.

Un rexistro, tamén chamado fila, é cada entrada individual que existe nunha táboa. Un rexistro é unha entidade horizontal nunha táboa.

Unha columna é unha entidade vertical nunha táboa que contén toda a información asociada a un campo específico dunha táboa.



---

*.ref: https://github.com/codershona/SQL-Server-Side-Learning/blob/master/README.md*.
