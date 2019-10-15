# Enlazando un sitio web desplegado en una máquina virtual linux en EC2 con una base de datos MySQL desplegada en AWS.

Repositorio con el código fuente: [SparkWebApp](https://github.com/jcamilovelandiab/SparkWebAppMySQL-AWS)

### 1. Crear un security group para la base de datos MySQL

a. Entramos en la consola de AWS, y en buscar servicios buscamos VPC, damos click en él.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql1.png)

b. Luego, en la parte izquierda de la página buscamos Security groups y damos click en la opción.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql2.png)

c. Damos click en el botón "Create Security Group"
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql3.png)

d. Le asignamos un nombr y una descripción, y dejamos el vpc por defecto. Luego, damos click en "create"
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql4.PNG)

e. Una vez creado el security group, seleccionamos el security group creado y le damos click en "Inbound rules" y luego "Edit rules"
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql5.png)

f. En tipo seleccionamos MYSQL/Aurora y en source seleccionamos "Anywhere" para que en un futuro podamos acceder a la base de datos.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql6.PNG)



### 2. Creando base de datos MySQL

a. En buscar servicios ingresamos RDS, y seleccionamos el servicio.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql7.png)

b. Damos click en "create database"
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql8.png)

c. Seleccionamos las siguientes opciones.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql9.PNG)


![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql10.PNG)

d. Ingresamos el nombre de la base de datos, e ingresamos el usuario y la contraseña
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql11.PNG)

e. Seleccionamos las siguientes opciones.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql12.PNG)

f. En conectividad seleccionamos el VPC por defecto, la opción SI en publicamente accesible para que un futuro podamos conectar nuestra máquina virtual linux con la base de datos.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql13.PNG)

g. En security group seleccionamos el que creamos anteriormente y el que viene por defecto
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql14.PNG)

h. En configuración adicional ponemos el nombre de la base de datos que va a tener inicialmente.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql15.png)

i. Damos click en "create database", y esperamos que inicie la base de datos, esto tarda normalmente unos minutos.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql16.PNG)

j. Luego de que la base de datos esté disponible, damos click sobre la base de datos que creamos.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql17.PNG)

k. Acá podemos ver las propiedades de la base de datos MySQL creada.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql18.PNG)

### 3. Probando la base de datos con DBeaver.

En éste caso elegí DBeaver para poder conectarme con la base de datos. Se puede probar con cualquier otra herramienta.

a. Abrimos DBeaver y damos click en crear nueva conexión.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql19.PNG)

b. Seleccionamos el motor SQL, MySQL.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql20.PNG)

c. Con las propiedades de la base de datos que vimos anteriormente llenamos los siguientes campos, y luego probamos la conexión con el botón Test Conection, y luego le damos finish.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql21.PNG)

d. Nos conectamos!!
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql22.PNG)

e. Ingresamos a la base de datos
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql23.PNG)

f. Añadimos un nuevo SQL editor y creamos una tabla llamada users.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql24.PNG)

g. Una vez creada la tabla ingresamos información a la tabla.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql25.PNG)

h. Damos click derecho sobre la tabla y luego click sobre refresh, en data podemos ver la información que contiene la tabla.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql26.PNG)

### 4. Creando máquina virtual en Linux.

a. En buscar servicios buscamos EC2 en la consola de AWS.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql27.png)

b. Para crear una instancia de una máquina virtual damos click en "Launch Instance"
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql28.PNG)

c. Seleccionamos la siguiente imagen para la máquina virtual.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql29.PNG)

d. Damos click en Next configure instance details.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql30.PNG)

e. Vamos a la ventana de Configure Security Groups y creamos un nuevo security groups, luego damos click en "Review and Lunch"
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql31.PNG)

f. Luego, damos click en el botón "Lunch"
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql32.PNG)

g. Creamos un nuevo par de llaves, le ponemos un nombre, y la descargamos. Es importante guardar ésta llave porque en un futuro nos vamos a conectar a la máquina virtual linux a través de SSH desde nuestro computador, si no tenemos la llave, no nos podremos conectar a la máquina virtual.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql33.PNG)

h. Luego de guardarla, damos click sobre el botón "Launch Instances"
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql34.PNG)

i. Luego de crearla damos click sobre el siguiente hiperlink.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql35.PNG)

j. Esperamos a que la máquina virtual inicie, y luego podemos ver que está corriendo.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql36.PNG)

### 5. Probando la aplicación Spark, y conectandola a la base de datos MySQL.

En éste caso utilicé Spark framework para poder interceptar solicitudes http. Voy a probar el proyecto que yo mismo realicé.

a. Vamos a la línea de comandos y clonamos el proyecto.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql37.PNG)

b. Lo abrimos con algún editor, en este caso yo utilicé Visual Studio Code.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql38.PNG)

c. Vamos a UserServices. Esta clase es la que realiza la conexión a la base de datos, reemplazamos todas las lineas connect con las propiedades de la base de datos que creamos. Luego de reemplazar todas las lineas guardamos los archivos.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql39.PNG)

d. Compilamos el proyecto.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql40.PNG)

e. Después de compilar vemos lo siguiente en la terminal.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql41.PNG)

f. Luego corremos el método main en la clase SparkWebApp.java
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql43.PNG)

g. Vemos que ya está corriendo el proyecto y está escuchando a través del puerto 4567
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql44.PNG)

h. Abrimos el navegador y vamos a localhost:4567/users, y podemos observar los usuarios que existen en la base de datos.
En la tabla observamos el usuario que creamos desde DBeaver.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql45.PNG)

i. Llenamos el formulario.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql46.PNG)

j. Damos click en en el botón Submit.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql47.PNG)

k.  Vemos que se registró correctamente la información. Luego damos click al link "Click to all users"
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql48.PNG)

l. En la tabla observamos el usuario que acabamos de crear.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql49.PNG)

m. Revisamos en DBeaver la tabla de usuarios y observamos que se pudo registrar correctamente.
<br />
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql50.PNG)



