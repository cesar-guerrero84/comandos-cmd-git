# ------comandos reparacion cmd------
##### En la ventana Símbolo de  Sistema(cmd) ejecutado como administrador, escriba SFC /SCANNOW y presione ENTER
#####Windows reparara cualquier archivo dañado o perdido que encuentre debe reiniciar una vez terminado el proceso
##### los siguientes comandos tambien son de reparacion automatica en cmd
- DISM /Online /Cleanup-Image /CheckHealth
- DISM /Online /Cleanup-Image /ScanHealth
- DISM /Online /Cleanup-Image /RestoreHealth
##### CHKDSK nos permite analizar toda la estructura de datos y reparar cualquier daño que se puedan detectar en un disco duro especifico
#####Un ejemplo para lanzar este comando y analizar nuestro disco duro es:
**chkdsk C: /F /R (la /F y /R** siempre deben ir despues del disco elegido) psdta ten en cuenta que este proceso aveces es largo y mientras esta
activo no podras usar algunos programas por que se estaran leyendo sus carpetas
# ----------comandos de git----------
- **git init** = es para indicar que vamos a empezar a usar git en un proyecto (carpeta) asi pasamos al working directory

- **git add**  = es para pasar los archivos del working directory al stage area

- **git status** = es para saber en que area de git esta nuestro proyecto (working directory , stage area , repository)

- **git commit -m "texto-info"** = envia el proye  desde  el staging hasta el repositorio 

- **git push + nombre de repositorio + el master o rama que quieras enviar** = es para subirlo a un respositorio remoto por ejemplo a un servidor para que otros desarrolladores puedan trabajar en el proyecto tambien

- **git pull + nombre de repositorio + el master o rama que quieras traer** = es para traer los cambios que han realizado otros desarrolladores y pasarlos al pc es como usar fetch y merge en un solo comando

- **git pull nombreDeRepositorio master/rama --allow-unrelated-histories** = trae la version de un repositorio remoto para hacer un commit fusionado con el repositorio local

- **git clone + link de repositorio **= es para hacer una copia de un repositorio en algun servidor y pasarlo a tu pc para que puedas trabajarlo

- **git checkout + direccion git commit + archivo** = trae las versiones de la rama del proyecto repositorio (master) para ver como era el archivo antes tambien sirve para cambiar a una rama especificando el nombre de la rama a la que quieres acceder, tambien si usas git chekout + master + archivo vuelves a la version que tengas en el master

- **git rm --cached** = borra el archivo del staging

- **git config** = muestra todas las configuraciones que tiene git 

- **git config --list** = para ver la configuracion por defecto de git

- **git config --list --show-origin** = para ver donde estan guardadas las configuraciones actuales de git

- **git config --global user.name "nombre de usuario"** = funciona para designar un nombre de usuario de git

- **git config --global user.email "email"** = funciona para designar un correo 

- **git add .** = para agregar todo lo de la carpeta al staging

- **git log** = muestra todas las modificaciones del proyecto presiona enter para verlos todos

- **git log --all** = muestra todos los cambios del proyecto

- **git log --all --graph** = muestra todos los cambios graficamente con lineas sobre las ramas

- **git log --all --graph --decorate  --oneline** = te muestra toda la historia del proyecto de forma mas grafica y comprimida

- **git show** = muestra todos los cambios de un archivo

- **git diff +la direccion git de un cambio + la direccion git del otro** = funciona para hacer comparaciones de los cambios hechos o para ver los cambios de un solo archivo usa solamente git diff

- **git reset + direccion del git commit + --hard o --soft** = esto es para volver a una antigua version de un commit con hard vuelves completamente a la version elegida y se borran las que este por delante y con soft vuelve pero el staging sigue siendo la version mas nueva

- **git log --stat** = funciona para ver los cambios especificos en el commit para salir de ese menu usa la letra Q

- **git fetch** = lo que hace es traer un repositorio de un server a tu master 

- **git merge** = pasa lo que pasaste del server al directorio de trabajo (pc)

- **git merge + rama** = lo que hace es fusionar la rama especificada con la rama donde te encuentras actualmente normalmente la master

- **git clone url_del_servidor_remoto** = Nos permite clonar un proyecto en un servidor remoto a nuestro repositorio local

- **git commit -am "mensaje"** = funciona para cuando modificaste un archivo ya trabajado y no lo has agragegado con git add este comando de una vez lo agrega y lo manda a un commit

- **git branch + nombre de la rama** = este comando crea una nueva rama de un repositorio master si escribes git branch solo te muestra las ramas creadas

- **git show-branch** = nos muestra las ramas que existen y su historia 

- **git show-branch --all** = es igual al de arriba pero con mas datos especificados

- **git branch -d nombreDeRama** = elimina una rama del repositorio local si pones la d mayuscula D lo borrara forzadamente

- **git remote add nombreDeRama + link del repositorio github** = este comando conecta nuestro proyecto a un repositorio github , git remote sin link puedes ver los repositorios conectados a github

- **git remote set-url origin + url repositorio github** = es para cambiar el link del repositorio de https a ssh por ejemplo

- **git remote -v** = para ver las opciones que podemos realizar a los respositorios recien traidos de un repositorio remoto

- **gitk** = te muestra toda la rama de las modificaciones del proyecto

- **git tag** = te muestra la lista de todos los tags guardados en el proyecto

- **git tag -a nombre del tag que quieras -m "mensaje o descripcion del tag" hash/direccion commit** = esto crea un tag en un commit especifico

- **git show-ref --tags** = te muestra todos los tags y a que commit estan asignados 

- **git tag -d nombreDeTag** = asi eliminas un tag desde git

- **git push nombreDeRepositorio :refs/tags/nombreDeTags** = esto elimina un tag del repositorio remoto 

- **git push nombreDeRepositorioRemoto --tags** = es para enviar a un repositorio remoto los tags de nuestro proyecto

- **git rebase master** = este comando pega una rama (estando en ella con git checkout) a la rama principal master de forma que pareciera que esa rama nunca huviera existido esto solo se debe hacer en local y no en repositorios remotos online por que cambia la historia tambien debes primero hacer rebase master en la rama donde esta el error o la que quieras unir y luego hacer el rebase en master llamando a la rama que quieres pegar al master asi evitas conflictos dificiles de solucionar esta practica es buena solo en casos de emergencias ya que cambia la historia de las ramas

- **git reset nombreDelArchivo** = reinicia un archivo que hayas agregado al stage con git add y lo saca del stage

# ------IMPORTANTE sobre git------
> Git reset y git rm son comandos con utilidades muy diferentes, pero aún así se confunden muy fácilmente.

>**git rm**
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

>Recuerda que git rm no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

>**git rm --cached** : Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
git reset
Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

>Este comando es muy peligroso y debemos usarlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

>Hay dos formas de usar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

>**git reset --soft** : Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
¡Pero todavía falta algo!

>**git reset HEAD** : Este es el comando para sacar archivos del área de Staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.
¿Por qué esto es importante?
Imagina el siguiente caso:

>Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando git add. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo pero ese cambio no debe ir en el próximo commit por ahora.

>¿Qué podemos hacer?

>Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

>¡Al usar git rm lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

>En cambio, si usamos git reset HEAD, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

>Conclusión: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.

# ------configuracion de llaves ssh------
####Primer paso: Generar tus llaves SSH. Recuerda que es muy buena idea proteger tu llave privada con una contraseña.

ssh-keygen -t rsa -b 4096 -C "tu@email.com"

Segundo paso: Terminar de configurar nuestro sistema.

En Windows y Linux:

#### Encender el "servidor" de llaves SSH de tu computadora:
eval $(ssh-agent -s)

#### Añadir tu llave SSH a este "servidor":
ssh-add ruta-donde-guardaste-tu-llave-privada

# --comandos de utilidad git y cmd--
-  **scape + shift + zz** = para salir de ciertas funciones
- **pwd** =  ubica tu carpeta actual
- **cd nombreDeCarpeta **= para navegar entre directorios
- **mkdir** = crea directorios (carpetas)
- **touch** = crea un nuevo documento
- **history** = toda la historia de los comandos ingresados 
- **!# o flecha hacia arriba** = para repetir un comando almacenado en history 
- **rm** = elimina archivos
- **--help** = informacion sobre los comandos 
- **rmdir** = elimina carpetas o directorios vacios
- **rm -r** = elimina carpetas con subcarpetas
- **rm -rf** = elimina toda una carpeta y su contenido a la fuerza
- **ls o dir** = para ver la lista de un directorio
- ** ls  -al** = para ver la lista de un directorio con los ocultos
- **cat NombreDeArchivo** = para ver el contenido de un archivo
- **vim NombreDeArchivo** = para editar el contenido de un archivo
