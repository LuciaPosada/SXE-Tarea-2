# Tarea 2

## 1.Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo

- Descarga la imagen: *sudo docker pull alpine*

- Comprueba que está en el equipo: *sudo docker image ls*

## 2.Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

- Crea un contenedor sin ponerle nombre: *sudo docker container create alpine*

- *sudo docker ps -a* No

- El nombre se genera de manera aleatoria. En mi caso el contenedor fue llamado quizzical_beaver

## 3.Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?

- Crea un contenedor y acceder a el: *sudo docker run -d --name dam_alp1 alpine tail -f /dev/null*

## 4. Comprueba que ip tiene y si puedes hacer un ping a google.com

- Comprueba la ip: *sudo docker inspect dam_alp1*

    - En la seccion NetworkSettings -> IPAddress

- Hacer ping: *sudo docker exec -it dam_alp1 ping google.com*

## 5. Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?

- Crea un contenedor: *sudo docker run -d --name dam_alp2 alpine tail -f /dev/null*

- *sudo docker exec -it dam_alp2 ping 172.17.0.2* Si, se puede hacer ping
