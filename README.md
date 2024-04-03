echo "# recuperacion" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/CarlosAlvarezDiaz/recuperacion.git
git push -u origin main

1 Descarga la imagen 'ubuntu' y comprueba que está en tu equipo.
2 Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre
3 Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?
4 Comprueba que ip tiene y si puedes hacer un ping a google.com
5 Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?
6 Sal del terminal, ¿que ocurrió con el contenedor?
7 ¿Cuanta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?
8 ¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.
