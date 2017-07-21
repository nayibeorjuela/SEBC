
//Hostname
MariaDB [(none)]> select @@hostname;
+------------------+
| @@hostname       |
+------------------+
| ip-172-31-44-156 |
+------------------+


// version de base de datos
MariaDB [(none)]> select version();
+----------------+
| version()      |
+----------------+
| 5.5.52-MariaDB |
+----------------+


//Bases de Datos
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
