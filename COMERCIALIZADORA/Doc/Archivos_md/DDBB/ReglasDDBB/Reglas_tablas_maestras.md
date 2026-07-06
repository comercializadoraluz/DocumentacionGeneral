# Reglas de tablas maestras

1. En la configuracion (CSVs) en el repo está solo la última version actualizada. Pero en las tablas estará la traza, estará todo.
2. Siempre se modificarán los datos maestros de la base de datos a través del repositorio dedicado. (A través del CI/CD) En local nunca se tendrán las contraseñas de produccion. Para ejecutarlo en local se creará otro proceso simulando el pipeline.
3. A los CSVs de las tablas maestras versionadas, se le puede hacer cualquier modificación (borrar, modificar, insertar nueva) (Para peajes ver ejemplo resolución de problemas)
4. En los CSVs de las tablas maestras NO versionadas, no puedes borrar (sí modificar e insertar nuevas)
5. NO pondremos IDS (los de los registros de la propia tabla) en los CSVs de las tablas maestras. Serán creados automáticamente.
6. NO habrá triggers para los cambios de las tablas maestras. Esto se hará por python