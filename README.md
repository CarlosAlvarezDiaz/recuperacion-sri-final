echo "# recuperacion" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/CarlosAlvarezDiaz/recuperacion.git
git push -u origin main

1 Descarga la imagen 'ubuntu' y comprueba que está en tu equipo.

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

Y despues comprobamos su estado con este otro comando:

       $docker ps -a
       CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS          PORTS     NAMES
       77953b3c9692   ubuntu    "/bin/bash"   42 seconds ago   Up 40 seconds                    focused_fermi
       
3 Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?
4 Comprueba que ip tiene y si puedes hacer un ping a google.com
5 Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?
6 Sal del terminal, ¿que ocurrió con el contenedor?
7 ¿Cuanta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?
8 ¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.
