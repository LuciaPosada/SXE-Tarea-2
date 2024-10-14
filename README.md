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
