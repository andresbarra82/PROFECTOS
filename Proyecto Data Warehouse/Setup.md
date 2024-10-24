### Para mostrar las habilidades de modelado vamos a comenzar con una base de pruebas. Adventure Works

#### Instalacion paso a paso para Windows 11: 

Instalación de Postgre

Instalacion de Ruby


How to set up the database:
Download Adventure Works 2014 OLTP Script.

Extract the .zip and copy all of the CSV files into the same folder, also containing update_csvs.rb file and install.sql.

Modify the CSVs to work with Postgres by running:

<div>
  <button onclick="copyCode()">Copiar código</button>
</div>

<pre id="codeBlock">
<code>
`ruby update_csvs.rb`
</code>
</pre>

Create the database and tables, import the data, and set up the views and keys with:

<pre style="margin: 0;">
<code>
psql -c "CREATE DATABASE \"Adventureworks\";"
psql -d Adventureworks < install.sql
</code>
</pre>


(If you do not have a database created for your user account then you may need to also add: -U postgres to the above two commands.)

All 68 tables are properly set up, and 11 of the 20 views are established. The ones not built are those that rely on XML functions like value and ref. To see a list of tables, open psql, and then connect to the database and show all the tables with these two commands:

<pre id="codeBlock">
<code>
\c "Adventureworks"
</code>
</pre>

<pre id="codeBlock">
<code>
\dt (humanresources|person|production|purchasing|sales).*
</code>
</pre>

<pre id="codeBlock">
<code>
psql -c "CREATE DATABASE \"Adventureworks\";" -U postgres -h localhost
</code>
</pre>

### Descarga y configuración de la base de datos AdventureWorks
Descarga el repositorio en https://github.com/lorint/AdventureWorks-for-Postgres
Ejecuta el siguiente comando de Git:

git clone https://github.com/lorint/AdventureWorks-for-Postgres.git

Este repositorio contiene los archivos para crear las tablas y vistas de la base de datos.

Descarga Adventure Works 2014 OLTP Script.
Contiene los archivos para llenar las tablas de la base de datos.

### Copia y pega el archivo AdventureWorks-oltp-install-script.zip en el directorio AdventureWorks-for-Postgres.

En tu terminal úbicate en el directorio AdventureWorks-for-Postgres y descomprime AdventureWorks-oltp-install-script.zip:

cd AdventureWorks-for-Postgres/
unzip AdventureWorks-oltp-install-script.zip 
#### Probablemente no funcione en cmd de windows este comando, pruba descomprimiendo los csv's a mano. 

En la terminal, ubicándote en el directorio AdventureWorks-for-Postgres, ejecuta el siguiente comando para convertir los archivos csv:

ruby update_csvs.rb

Activa la conexión con postgresql:

sudo service postgresql start

#### o si no funciona como en mi caso (windows 11)
Abrir el Administrador de Servicios:
Presiona Win + R, escribe services.msc y presiona Enter.
Buscar el servicio de PostgreSQL:
En la lista de servicios, busca algo como postgresql-x64-<version>.
#### Iniciar el servicio:
Haz clic derecho sobre el servicio y selecciona “Iniciar”.

Crea la base de datos con el siguiente comando de PostgreSQL:

psql -c "CREATE DATABASE \"Adventureworks\";" -U postgres -h localhost

Ejecuta el script que llena las tablas de la base de datos:

psql -d Adventureworks < install.sql -U postgres -h localhost


### Conecta tu base de datos en DBeaver o pgAdmin.

Abre DBeaver o pgAdmin.

Selecciona la opción para crear una nueva conexión.

Selecciona PostgreSQL en la lista de bases de datos.

Ingresa la información de conexión necesaria en la pestaña.

Host: localhost
Port: 5432
Base de datos: Adventureworks
Nombre de usuario: postgres
Password: la que tengas de tu user de postgresql.



