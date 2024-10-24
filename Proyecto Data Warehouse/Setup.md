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
