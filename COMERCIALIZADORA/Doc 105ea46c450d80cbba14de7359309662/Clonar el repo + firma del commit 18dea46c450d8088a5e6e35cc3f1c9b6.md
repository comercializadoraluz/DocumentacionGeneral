# Clonar el repo + firma del commit

Para bajarte el repo → usa https (y no ssh porque en windows, para hacer pull y push tendría que estar logeandote continuamente)

Por seguridad, ya que no usamos ssh, usamos la firma del commit ( hay que crearla en github)

![image.png](Clonar%20el%20repo%20+%20firma%20del%20commit%2018dea46c450d8088a5e6e35cc3f1c9b6/image.png)

C:\Users\francisco.martinez\.ssh

git log --show-signature 

Si no lo tienes configurado lo verás así: (aunque realmente sí que esté firmado)

![image.png](Clonar%20el%20repo%20+%20firma%20del%20commit%2018dea46c450d8088a5e6e35cc3f1c9b6/image%201.png)

Si está bien configurado sale así:

![image.png](Clonar%20el%20repo%20+%20firma%20del%20commit%2018dea46c450d8088a5e6e35cc3f1c9b6/image%202.png)

Para tus commits sale good git, para las de tus compis good git no principal matched pq no lo tienes configurado en tu local las firmas de los demás, (ni falta que hace ya está en github)
En github si sale verified

![image.png](Clonar%20el%20repo%20+%20firma%20del%20commit%2018dea46c450d8088a5e6e35cc3f1c9b6/image%203.png)