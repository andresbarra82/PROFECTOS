# Proceso de LookUp o "Búsqueda de Valor en Flujo" (Pnetrajo 10.2 Version Desarrollador)

Ponemos de que campo a que campo queremos encontrar la coincidencia: en este caso: cod_cliente y codigo_cliente
para traernos el ID y en el caso de que vengan en nulo le ponga un "-1" como valor. De esta manera se identifica que los valores son nuevos

![image](https://github.com/user-attachments/assets/7ce0953a-07c6-49ea-9a55-512d9582877b)

Se buscan los registros que vienen del transaccional, los cruzamos con el dimensional y los registros que sean nuevos les asignaremos un id nuevo
y los registros que ya existan le vamos a asignar el mismo id




