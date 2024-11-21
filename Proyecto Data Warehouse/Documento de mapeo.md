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
- Field name: indicador_insert_update id_cliente, Replace by value from field: id_cliente

![image](https://github.com/user-attachments/assets/06e15f81-d710-477a-bbc6-42da19fda421)


Luego agregar un filtro, si el valor el id es -1

![image](https://github.com/user-attachments/assets/a578a744-331c-480e-a02c-3eb4a2eb30a6)

Luego se crea una constante nueva para ver cuando no se cumple la condicion

![image](https://github.com/user-attachments/assets/ee6269a0-887a-4b2a-8b12-53a32700043f)

Si no se cumple esa condicion entonces le va a asignar el mismo id que ya tiene

![image](https://github.com/user-attachments/assets/f900917a-d8ee-4cbd-bbcb-cd61b48c47b7)

Le decimos  a al nueva contante que tome el valor de max_cliente_id del id_cliente

![image](https://github.com/user-attachments/assets/d9c28715-e8d4-4888-a725-766d8510658b)

Luego se le agrega una variable positiva cuando el registro que ingresa si es nuevo:

se utiliza el metodo para que comienze el incremental: ${Max_registro}

![image](https://github.com/user-attachments/assets/aa476d0d-8869-4c53-8306-1747bc53ea9c)


Una vez chequado todo, vamos a formula, preview, configurar, variables: poner en 0 y de ahí comenzar 

![image](https://github.com/user-attachments/assets/3d649841-d0b8-4125-b2fc-8692f90a0394)

A la formula hay que agregarle:
El nombre del nuevo campo: "id_calculado" \
La formula: IF(([id_cliente]=-1); [max_cliente_id]; [id_cliente]) \
y en Reemplazar valor: "max_cliente_id" para que tome el valor del campo calculado si es que el id_cliente era -1 es decir no existia. \
![image](https://github.com/user-attachments/assets/14307522-9119-4fc9-be5c-fa9cef920007)




