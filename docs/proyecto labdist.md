## Ejercicio de Git - proyecto Labdist

<div style= "background-color: rgb(165, 223, 244)">
    <p>
        Módulo: Despliegue de aplicaciones Web - Distancia
    </p>
   <p>
       Alumno: Alfonso Dapena Cores
    </p> 
    </div>




[toc]

### 1.Trabajo en local

##### 1.1 Inicializar repositorio

- En primer lugar , escribiremos el siguiente comando para que el historial de ramas Git se mantenga como un árbol: 

  ```bash
  git config -- global merge. ff false
  ```

- A continuación Inicializamos el repositorio Git en la carpeta `labdist`, donde agregaremos los archivos proporcionados en el aula virtual. Una vez, agregados los archivos, renombraremos la rama master a `main`,  realizaremos nuestro primer commit y mostraremos el log del repositorio, valiéndonos del siguiente código:

  ```bash
  git init # inicializamos el repositorio
  git add . # añadimos los archivos proporcionados en el aula virtual
  git branch -m "main" # renombramos la rama master a main
  git commit -m "Añadiendo archivos" # realizamos el primer commit
  git log # comprobamos el historial del repositorio
  git status # comprobamos que nuestro repositorio esté actualizado
  ```

![](./proyecto%20labdist.assets/captura%201-1739541574056-8.JPG)

##### 1.2 Incluimos en el repositorio el archivo `.gitignore`

- A continuación incluiremos un fichero `.gitignore` para que los ficheros `README.MD`, `LICENCE.txt`, y `passwords.txt` sean ignorados por el control de versiones. Después de realizaremos el commit y mostraremos los logs del repositorio en una línea con el siguiente código: 

```bash
cat > .gitignore # creamos el fichero gitignore con las lineas
README.md
LICENCE.txt
passwords.txt
git status # comprobamos los cambios pendientes en nuestro repositorio
git add. # añadimos las modificaciones a la zona de intercambio temporal de nuestro repositorio
git commit -m "añadido archivo" # realizamos el commit y añadimos nuestro archivo al repositorio y lo actualizamos
git log --oneline # mostramos el historial del repositorio en una linea
```

<img src="./proyecto%20labdist.assets/captura%202.JPG" style="zoom:80%;" />

##### 1.3 Creación archivos `README.md`,  `LICENCE.txt`,  y  `passwords.txt`.

- En nuestro repositorio, crearemos los archivos `README.md`, ` LICENCE.txt`,  y `passwords.txt` , con algún contenido. Mostraremos el estado del repositorio y también el de los archivos ignorados con los siguientes comandos

```bash
cat > README.md # creamos el archivo README.md
cat > LICENCE.txt # creamos el archivo LICENCE.txt
cat > passwords.txt # creamos el archivo passwords.txt
git status # comprobamos el estado del repositorio
git ls-files --others -i --exclude-standard # comprobamos los archivos que son ignorados por nuestro control de revisiones
```

<img src="./proyecto%20labdist.assets/captura%203.JPG" style="zoom:100%;" />

##### 1.4 Creación rama `feature-estilos`.

- En nuestro repositorio creamos la rama `feature-estilos` y nos cambiamos a ella. A continuación, modificaremos el archivo `estilos.css`, modificando las propiedades del color del`body`, y del `h2`,  ya  el `background-color` del `header`y del `footer`  a `#2a2a21`. Una vez realizados los cambios comprobaremos el estado del repositorio, añadiremos los cambios, y realizaremos un commit con el mensaje "actualizados estilos a azules". 

```bash
git branch "feature-estilos" # creamos la rama "feature-estilos"
git checkout feature-estilos # pasamos de la rama "main" a la rama "feature-estilos"
#modificamos el archivo estilos.css 
git status # comprobamos el estado del repositorio: se nos mostrará un mensaje en rojo en el que se indica "modified: css/estilos.css"
git add . #añadimos el archivo modificado a la zona de intercambio temporal
git commit -m "actualizados estilos a azules" # confirmaremos el cambio en nuestro repositorio
git status # comprobamos el estado de nuestro repositorio, que nos indicará que no hay commit pendiente y el repositorio actualizado
```

![](./proyecto%20labdist.assets/captura%204.JPG)

##### 1.5 Modificación archivo  `index.html` 

- Regresamos a la rama `main`, y en el archivo `index.html `añadimos un comentario donde vamos a indicar nuestro nombre como autor de la página. A continuación, mostraremos el estado del repositorio añadiremos los cambios, y realizaremos un commit con el mensaje "añadido autor en index". Finalmente, mostraremos los logs del repositorio en una línea, gráficamente y con decoración.

```bash
git checkout main # regresamos a la rama "main"
git status # comprobamos el estatus del repositorio, que nos mostrará en rojo "modified : index.html"
git add . # añadimos el archivo modificado "index.html" a la zona de intercambio temporal
git commit -m "añadido autor en index" # confirmamos los cambios y actualizamos el repositorio
git log --oneline --graph --decorate # mostramos los logs del repositorio en una línea, graficamente y con decoración
```

![](./proyecto%20labdist.assets/captura%205.JPG)

##### 1.6 Fusión rama `feature-estilos` en la rama `main`.

- Fusionaremos la rama `feature-estilos` en la rama `main` y mostraremos los logs del repositorio en una línea, gráficamente y con decoración

  ```bash
  git merge -m "fusionando rama feature-estilos" feature-estilos # con la instrucción "merge" realizamos la fusión
  git log --oneline --graph --decorate #mostramos los logs del repositorio en una línea, graficamente y con decoración
  ```

  ![](./proyecto%20labdist.assets/Captura%206.JPG)



### 2.Trabajo en remoto

##### 2.1 Añadimos el repositorio `labdist` a Soucertree.

- Abrimos la aplicación Soucertree y en hacemos click en la pestaña `Create`, y buscamos la ruta donde tenemos almacenado nuestro repositorio. 

![](./proyecto%20labdist.assets/captura1%20remoto.JPG)



- Pinchamos en el botón Create:

  

![](./proyecto%20labdist.assets/captura2%20remoto-1739551234818-6.JPG)



- Y ya tenemos nuestro repositorio en Soucetree:

  

![](./proyecto%20labdist.assets/captura3%20remoto.JPG)

##### 2.2 Creación repositorio remoto en GitHub y subida del repositorio local

- En primer lugar, accedemos al sitio Web de Github, y, después de logearnos, creamos un nuevo repositorio remoto, pinchando en la pestaña de New:

  ![](./proyecto%20labdist.assets/captura4%20remoto.JPG)



- Seguimos las instrucciones y creamos nuestro repositorio remoto, al que denominaremos `Tarea2_alfonso_dapena_cores`



![](./proyecto%20labdist.assets/captura5%20remoto.JPG)

![](./proyecto%20labdist.assets/captura6%20remoto.JPG)

- Una vez creado nuestro repositorio remoto, copiaremos la url del repositorio      [https://github.com/orv5714/Tarea2_alfonso_dapena_cores.git]()    para añadirla a nuestro repositorio local y de esa manera poder subir nuestro repositorio local al remoto:

![](./proyecto%20labdist.assets/captura7%20remoto.JPG)

- Regresamos a nuestro repositorio en Sourcetree y en la pestaña `Settings` opción `Remotes` añadiremos la url del repositorio remoto que acabamos de crear, pinchando en `Add`: 

![](./proyecto%20labdist.assets/captura8%20remoto.JPG)



- Introduciremos los datos del repositorio remoto y guardamos los cambios:



![](./proyecto%20labdist.assets/captura9%20remoto.JPG)

![](./proyecto%20labdist.assets/captura10%20remoto.JPG)



- Una vez añadido nuestro repositorio remoto, podemos subir nuestro repositorio local a este, mediante la instrucción `push`:

![](./proyecto%20labdist.assets/captura11%20remoto.JPG)

![](./proyecto%20labdist.assets/captura12%20remoto.JPG)



- En Sourcetree, pincharemos la bola del mundo que indica "Remote" y podremos comprobar cómo se ha subido una copia de nuestro repositorio local al repositorio remoto.

![](./proyecto%20labdist.assets/captura13%20remoto.JPG)

![](./proyecto%20labdist.assets/captura14%20remoto.JPG)

##### 2.3 Creación rama `feature-index` en el repositorio local. Modificación archivo `index.html` y subida de cambios al repositorio remoto.

- En Sourcetree, pincharemos en la pestaña branch y crearemos nuestra nueva rama `feature-index`.

![](./proyecto%20labdist.assets/captura15remoto.JPG)

![](./proyecto%20labdist.assets/captura16remoto.JPG)



- Después de modificar el archivo `index.html`, en la ventana `Unstaged files` se nos mostrará en amarillo el archivo `index.html` sobre el que hemos hecho las modificaciones. En la ventana de la derecha se recogen los cambios en verde. 

  

![](./proyecto%20labdist.assets/captura17remoto-1739552863402-23.JPG)



- A continuación, realizaremos un commit, para guardar los cambios en nuestro repositorio

![](./proyecto%20labdist.assets/captura18remoto.JPG)



- Después de realizado el cambio, todos los archivos se mostraran en verde. Esto quiere decir que esta rama está actualizada, y ya podemos subir los cambios a nuestro repositorio remoto, con la instrucción `push`. 

![](./proyecto%20labdist.assets/captura19remoto.JPG)



- Accedemos a nuestro repositorio remoto y observamos que se han realizado los cambios

  

![](./proyecto%20labdist.assets/captura20remoto.JPG)

##### 2.4 Fusión rama `feature-index` en la rama `main`



- Regresamos a nuestro repositorio local y fusionamos la rama `feature-index` en la rama `main`, pinchando en la pestaña "Merge".

![](./proyecto%20labdist.assets/captura21remoto.JPG)

![](./proyecto%20labdist.assets/captura22remoto.JPG)

![](./proyecto%20labdist.assets/captura23remoto.JPG)



##### 2.5 Modificación fichero `contacto.html`, mostrar cambios pendientes y las diferencias y añadir cambios y realizar commit.



- En primer lugar, modificamos el fichero `contacto.html`, y comprobamos los cambios y diferencias en la aplicación.

![](./proyecto%20labdist.assets/captura24remoto-1739553816043-32.JPG)



- Añadimos los cambios y realizamos un commit para guardarlos en nuestro repositorio local:

  

![](./proyecto%20labdist.assets/captura25remoto.JPG)



##### 2.6 Deshacemos el último commit, y comprobamos que el archivo no ha sido modificado.

- En Sourcetree, en el apartado `History`, buscamos la actualización anterior al último commit, y clickamos el botón derecho del ratón y seleccionamos la opción `Reset current branch to this commit`:

![](./proyecto%20labdist.assets/captura26remoto-1739554128999-36.JPG)

![](./proyecto%20labdist.assets/captura27remoto.JPG)



- Y seleccionamos la opción `Hard - discard all working copy changes`

![](./proyecto%20labdist.assets/captura28remoto.JPG)



-  Y, finalmente comprobamos que las líneas borradas se han recuperado y que no hay ningún archivo pendiente en el repositorio

  

![](./proyecto%20labdist.assets/captura29remoto.JPG)



##### 2.7 Creación rama `feature-mapa`, modificación archivo `contacto.html`, y confirmación de los cambios en el repositorio local

- En primer lugar creamos la rama `feature-mapa`:

![](./proyecto%20labdist.assets/captura30remoto.JPG)

![](./proyecto%20labdist.assets/captura31remoto.JPG)



- Modificamos el archivo `contacto.htm`, añadimos los cambios al repositorio y los confirmamos con un commit:

![](./proyecto%20labdist.assets/captura32remoto.JPG)

![](./proyecto%20labdist.assets/captura33remoto.JPG)



##### 2.8 Subimos los cambios al repositorio remoto



- Tras realizar el último commit, realizamos un `push` para subir los cambios en nuestro repositorio local al remoto

![](./proyecto%20labdist.assets/captura34remoto.JPG)



-  Y mostramos los cambios en el repositorio remoto:

![](./proyecto%20labdist.assets/captura%20estado.jpg)

![](./proyecto%20labdist.assets/captura36remoto.JPG)

##### 2.9 En GitHub, en la rama `main` fusionamos la rama `feature-mapa`. Bajaremos los cambios al repositorio local y los dejaremos sincronizados.

- En primer lugar, accedemos a nuestro repositorio remoto. Observamos que en la parte derecha, figura una advertencia en verde que indica `Compare & pull request`. Debemos de clickar en ella para realizar la fusión.

![](./proyecto%20labdist.assets/captura35remoto-1739555236279-49.JPG)

- Se nos mostrará otra pantalla, en la que se nos indica que podemos realizar el merge "Able to merge", y podremos añadir un comentario. Después pincharemos, en la opción `Create pull request`

![](./proyecto%20labdist.assets/captura37remoto.JPG)

- Ya continuación pulsamos `Merge pull request`.



![](./proyecto%20labdist.assets/captura38remoto.JPG)



- Y confirmamos el `merge`

![](./proyecto%20labdist.assets/captura39remoto.JPG)



- Con esto, ya habremos fusionado las ramas

![](./proyecto%20labdist.assets/captura40remoto.JPG)

![](./proyecto%20labdist.assets/captura41remoto.JPG)

- Ahora debemos llevar los cambios de nuestro repositorio remoto al local. Para ello regresamos a Sourcetree, y observamos que en la ventana se nos muestra un aviso el la pestaña `Pull`. Por lo que clickaremos en ella y realizaremos el proceso para bajar los cambios de nuestro repositorio remoto al local:

![](./proyecto%20labdist.assets/captura42remoto.JPG)

![](./proyecto%20labdist.assets/captura43remoto.JPG)



- Una vez realizado el Pull, la aplicación nos muestra que hay un `push` pendiente, por lo que procedemos a subir a nuestro repositorio remoto el cambio

![](./proyecto%20labdist.assets/captura44-ojo%20con%20el%20push-remoto.JPG)

![](./proyecto%20labdist.assets/captura45-ojo%20con%20el%20push-remoto.JPG)

-  Ahora ya tendríamos nuestro repositorio local actualizado.

  ![](./proyecto%20labdist.assets/captura46-ojo%20con%20el%20push-remoto.JPG)

- Regresamos a nuestro repositorio remoto y comprobamos que nuestro repositorio está actualizado y que el fichero `contacto.html`es igual en nuestro repositorio local...

![](./proyecto%20labdist.assets/captura47-ojo%20con%20el%20push-remoto.JPG)

- ... y en el remoto:

![](./proyecto%20labdist.assets/captura48-ojo%20con%20el%20push-remoto.JPG)

![](./proyecto%20labdist.assets/captura49-ojo%20con%20el%20push-remoto.JPG)



### 3 Conflictos



##### 3.1 Creamos una rama `hot-fix`, nos cambiamos a ella y añadimos el siguiente código al fichero `script.js.`. Una vez realizado el cambio lo confirmaremos y haremos un commit.

```javascript
 if (mensaje.value.trim() === "") {
 alert("Por favor, ingrese un mensaje.");
 valid = false;
	}
```

- Creamos la rama `hot-fix`en Sourcetree, añadimos el fichero y confirmamos el cambio con un commit "corregido problema en script.js".

![](./proyecto%20labdist.assets/captura50.JPG)

![](./proyecto%20labdist.assets/captura51la%20siguiente%20mejor.JPG)

![](./proyecto%20labdist.assets/captura52.JPG)

![](./proyecto%20labdist.assets/captura53.JPG)



##### 3.2 Regresamos a la rama `main`, y modificamos el fichero `script.js` con los cambios indicados en el siguiente código. Confirmamos el cambio  con un commit.

```javascript
 if (mensaje.value.trim() === "") {
 alert("Ingrese un mensaje, por favor");
 valid = false;
 }
```

- Cambiamos a la rama `main`, pinchando sobre esta en el menú vertical lateral, y, después de modificar el archivo y añadirlo a la zona de intercambio temporal, realizamos el commit "corregido problema en script.js rama main"

![](./proyecto%20labdist.assets/captura55.JPG)



##### 3.3 Fusionamos la rama `hot-fix`, en `main`, y resolución del conflicto.



- Primero seleccionamos en el `History` la rama que vamos a fusionar, en este caso sería la rama `hot-fix`, como se muestra en la siguiente captura

![](./proyecto%20labdist.assets/captura56.JPG)



-  Y realizamos la fusión `Merge`. En la pantalla se nos mostrará un mensaje indicando que hay un conflicto, pues estamos fusionando un archivo con dos contenidos diferentes en cada rama

![](./proyecto%20labdist.assets/captura57.JPG)

- En el área `Unstaged files`, seleccionamos el archivo en amarillo `script.js`, y observamos en la ventana de la derecha las diferencias entre las dos versiones, `main`, la que indica `HEAD`, y la otra rama `hot-fix`. Hacemos click en el botón derecho del ratón y en la opción "resolver el conflicto", lo resolvemos manteniendo el código de la rama principal.

![](./proyecto%20labdist.assets/captura58.JPG)

![](./proyecto%20labdist.assets/captura55%20resuelvo%20usando%20el%20mio-main.JPG)

- A continuación realizamos el commit, para guardar los cambios y comprobamos que el conflicto ha quedado resuelto comprobando el historial de las ramas

![](./proyecto%20labdist.assets/captura59.JPG)

![](./proyecto%20labdist.assets/captura60.JPG)

- A continuación, tenemos que actualizar en nuestro repositorio remoto los cambios. Hacemos un `pull`, y subimos el repositorio local al remoto.

![](./proyecto%20labdist.assets/captura61.JPG)

![](./proyecto%20labdist.assets/captura62.JPG)

-  Y, por último, comprobamos en nuestro repositorio remoto que se han subido todos los cambios y tenemos una nueva rama `hot-fix`.