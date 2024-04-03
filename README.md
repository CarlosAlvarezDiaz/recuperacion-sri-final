echo "# recuperacion" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/CarlosAlvarezDiaz/recuperacion.git
git push -u origin main

1 Descarga la imagen 'ubuntu' y comprueba que está en tu equipo.

Utilizaremos el comando docker pull ubuntu:

       $ docker pull ubuntu
        Using default tag: latest
        latest: Pulling from library/ubuntu
        bccd10f490ab: Pull complete
        Digest: sha256:77906da86b60585ce12215807090eb327e7386c8fafb5402369e421f44eff17e
        Status: Downloaded newer image for ubuntu:latest
        docker.io/library/ubuntu:latest
        
2 Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

Primero creamos el contenedor con el siguiente comando:

       $ docker run -it  ubuntu

Y despues comprobamos su estado con este otro comando, el cual tambien nos dara su nombre:

       $docker ps -a
       CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS          PORTS     NAMES
       77953b3c9692   ubuntu    "/bin/bash"   42 seconds ago   Up 40 seconds       focused_fermi
       
3 Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?

Al igual que en el ejercicio anterior, empezaremos con el comando docker run:
       
       $ docker run -it --name ubu1 ubuntu

Y para acceder a el usaremos el comando docker exec:

       $ docker exec -it ubu1 bash

4 Comprueba que ip tiene y si puedes hacer un ping a google.com

Primero usaremos el comando docker inspect para comprobar su ip:

       $ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ubu1
172.17.0.3

Para comprobar si se puede hacer ping a google.com, primero debemos hacer click derecho sobre el contenedor mientras este activo y le damos a attach shell

Acto seguido debemos lanzar los comandos apt-get update y apt-get install:

       $ apt-get update
         apt-get install iputils-ping

Una vez hecho eso, hacemos ping a google.com:

       $ ping google.com
              PING google.com (142.250.185.14) 56(84) bytes of data.
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=1 ttl=63 time=17.6 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=2 ttl=63 time=18.3 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=3 ttl=63 time=17.4 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=4 ttl=63 time=18.4 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=5 ttl=63 time=18.0 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=6 ttl=63 time=18.5 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=7 ttl=63 time=17.6 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=8 ttl=63 time=18.3 ms
              64 bytes from 142.250.185.14 (142.250.185.14): icmp_seq=9 ttl=63 time=17.9 ms

              --- google.com ping statistics ---
              9 packets transmitted, 9 received, 0% packet loss, time 8011ms
              rtt min/avg/max/mdev = 17.395/17.991/18.537/0.374 ms
              
5 Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?
6 Sal del terminal, ¿que ocurrió con el contenedor?
7 ¿Cuanta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?
8 ¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.
