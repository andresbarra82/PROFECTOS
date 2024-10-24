Para mostrar las habilidades de modelado vamos a comenzar con una base de pruebas. Adventure Works

Instalacion paso a paso para Windows 11: 

Instalación de Postgre

Instalacion de Ruby


How to set up the database:
Download Adventure Works 2014 OLTP Script.

Extract the .zip and copy all of the CSV files into the same folder, also containing update_csvs.rb file and install.sql.

Modify the CSVs to work with Postgres by running:

`ruby update_csvs.rb`

Create the database and tables, import the data, and set up the views and keys with:

`psql -c "CREATE DATABASE \"Adventureworks\";"
psql -d Adventureworks < install.sql` 

(If you do not have a database created for your user account then you may need to also add: -U postgres to the above two commands.)

All 68 tables are properly set up, and 11 of the 20 views are established. The ones not built are those that rely on XML functions like value and ref. To see a list of tables, open psql, and then connect to the database and show all the tables with these two commands:

`\c "Adventureworks"`

`\dt (humanresources|person|production|purchasing|sales).*`


`psql -c "CREATE DATABASE \"Adventureworks\";" -U postgres -h localhost`
