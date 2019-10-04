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

e.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql11.PNG)

f.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql12.PNG)

g.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql13.PNG)

h.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql14.PNG)

i.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql15.png)

j.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql16.PNG)

k.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql17.PNG)

l.
![](https://github.com/jcamilovelandiab/ArchitecturalPatternsAWS/blob/master/EC2-MySQL/images/ec2-mysql18.PNG)
