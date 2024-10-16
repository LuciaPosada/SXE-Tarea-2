# Tarea 2

## 1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo

- Descarga la imagen: *sudo docker pull alpine*

    ![Comando Paso1](/img/paso1_1.png)

- Comprueba que está en el equipo: *sudo docker image ls*

    ![Comando Paso1](/img/paso1_2.png)

## 2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

- Crea un contenedor sin ponerle nombre: *sudo docker container create alpine*

- Listar contenedores: *sudo docker ps -a*

    ![Comando Paso2](/img/paso2.png)

    Utilizando el comando *container create*, los contenedores no se ejecutan despues de su creacion, al contrario del comando *run*.

El nombre se genera de manera aleatoria. En mi caso el contenedor fue llamado quizzical_beaver

## 3. Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?

- Crea un contenedor que se mantenga en ejecucion: *sudo docker run -d --name dam_alp1 alpine tail -f /dev/null*

    ![Comando Paso3](/img/paso3_1.png)

- Acceder al contenedor: *sudo docker exec -it dam_alp1 sh*

    ![Comando Paso3](/img/paso3_2.png)

## 4. Comprueba que ip tiene y si puedes hacer un ping a google.com

- Comprueba la ip: *sudo docker inspect dam_alp1*

    En la seccion NetworkSettings -> IPAddress

    ![Comando Paso4](/img/paso4_1.png)

- Hacer ping:
    - Opcion 1: *sudo docker exec -it dam_alp1 ping google.com*
    - Opcion 2: (Desde la shell del contenedor) *ping google.com*

        ![Comando Paso4](/img/paso4_2.png)

## 5. Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?

- Crea un contenedor: *sudo docker run -d --name dam_alp2 alpine tail -f /dev/null*

- Ping: *sudo docker exec -it dam_alp2 ping 172.17.0.2*

    ![Comando Paso5](/img/paso5.png)

    Si, se puede hacer ping

## 6. Sal del terminal, ¿que ocurrió con el contenedor?

- Salir del terminal:
    - Opcion 1: *exit*
    - Opcion 2: Ctrl + D

Al salir del terminal se cierra el contenedor

## 7. ¿Cuanta memoria en el disco duro ocupaste?

- Ver uso de memoria total: *sudo docker system df*

    ![Comando Paso7](/img/paso7_1.png)

- Ver uso de memoria especifico: *sudo docker ps -as*

    ![Comando Paso7](/img/paso7_2.png) ![Comando Paso7](/img/paso7_3.png)

## 8. ¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?

- Ver RAM: *sudo docker status*

    ![Comando Paso8](/img/paso8.png)

