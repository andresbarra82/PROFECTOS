# Proceso de LookUp o "Búsqueda de Valor en Flujo" (Pnetrajo 10.2 Version Desarrollador)

Ponemos de que campo a que campo queremos encontrar la coincidencia: en este caso: cod_cliente y codigo_cliente
para traernos el ID y en el caso de que vengan en nulo le ponga un "-1" como valor. De esta manera se identifica que los valores son nuevos

![image](https://github.com/user-attachments/assets/7ce0953a-07c6-49ea-9a55-512d9582877b)

Se buscan los registros que vienen del transaccional, los cruzamos con el dimensional y los registros que sean nuevos les asignaremos un id nuevo
y los registros que ya existan le vamos a asignar el mismo id

Luego Agregamos el System info (de la carpeta Input) o informacion de sistema, para agregarle la fecha de carga:
Nombre load_date y funcion: fecha_variable

![image](https://github.com/user-attachments/assets/952e6e95-58b9-460c-b57c-f2ae5256dd32)

Luego podemos hacer un preview hasta el momento para ver como viene la transformación

![image](https://github.com/user-attachments/assets/d3eae549-43de-4027-afa1-808968517f1d)

Luego agregamos una constante para identificar si es un valor nuevo que hay que insertarlo o actualizarlo

![image](https://github.com/user-attachments/assets/9a3dd4ea-4ab2-4f99-baca-954deff240c9)

Luego setear el valor de la contante con set field value:

![image](https://github.com/user-attachments/assets/ae03bdd6-5461-4a8b-a958-0eda5bfec440)

