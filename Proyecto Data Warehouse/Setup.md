### Para mostrar las habilidades de modelado vamos a comenzar con una base de pruebas. 
Adventure Works

#### Instalacion paso a paso para Windows 11: 

### Instalación de Postgre

Vamos a instalar PostgreSQL en nuestra computadora. A continuación veremos el paso a paso y algunos consejos útiles para instalar y configurar correctamente PostgreSQL en nuestro equipo. En éste caso, usaremos Windows, pero los pasos son bastante similares entre los diferentes sistemas operativos.

Primer paso: ir a https://www.postgresql.org/.

### Instalacion de Ruby en Windows
Descarga el instalador de Ruby desde la página oficial de Ruby para Windows: https://rubyinstaller.org/downloads/
Selecciona la versión de Ruby que deseas instalar.
Ejecuta el instalador y sigue las instrucciones del asistente de instalación.
Una vez completada la instalación, abre la línea de comandos de Windows (cmd.exe) y escribe ruby -v para verificar que la instalación se haya realizado correctamente.

## Como instalar la base de datos de pruebas:

### Descarga y configuración de la base de datos AdventureWorks
Descarga el repositorio en https://github.com/lorint/AdventureWorks-for-Postgres
o en: 
Download <a href="https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks-oltp-install-script.zip">Adventure Works 2014 OLTP Script.</a>

#### Configuracion de las tablas
Ejecuta en consola el siguiente comando de Git para descargar la configuracion de las tablas:
<pre id="codeBlock">
<code>
git clone https://github.com/lorint/AdventureWorks-for-Postgres.git
</code>
</pre>

Contiene los archivos para llenar las tablas de la base de datos.

### Copia y pega el archivo AdventureWorks-oltp-install-script.zip en el directorio AdventureWorks-for-Postgres.

En tu terminal úbicate en el directorio AdventureWorks-for-Postgres y descomprime AdventureWorks-oltp-install-script.zip:

`cd AdventureWorks-for-Postgres/`

`unzip AdventureWorks-oltp-install-script.zip`
#### Probablemente no funcione en cmd de windows este comando, pruba descomprimiendo los csv's a mano. 

En la terminal, ubicándote en el directorio AdventureWorks-for-Postgres, ejecuta el siguiente comando para convertir los archivos csv:

`ruby update_csvs.rb`

Activa la conexión con postgresql:

`sudo service postgresql start`

#### o si no funciona como en mi caso (windows 11)
Abrir el Administrador de Servicios:
Presiona Win + R, escribe services.msc y presiona Enter.
Buscar el servicio de PostgreSQL:
En la lista de servicios, busca algo como postgresql-x64-<version>.
#### Iniciar el servicio:
Haz clic derecho sobre el servicio y selecciona “Iniciar”.

Crea la base de datos con el siguiente comando de PostgreSQL:

`psql -c "CREATE DATABASE \"Adventureworks\";" -U postgres -h localhost`

Ejecuta el script que llena las tablas de la base de datos:

`psql -d Adventureworks < install.sql -U postgres -h localhost`


### Conecta tu base de datos en DBeaver o pgAdmin.

Abre DBeaver o pgAdmin.

Selecciona la opción para crear una nueva conexión.

Selecciona PostgreSQL en la lista de bases de datos.

Ingresa la información de conexión necesaria en la pestaña.

```
Host: localhost
Port: 5432
Base de datos: Adventureworks
Nombre de usuario: postgres
Password: la que tengas de tu user de postgresql.
