# **CURSO GIT**
## Repositorio
Es todo proyecto que tiene un seguimiento por Git.
## COMANDO: git init
Comando para inicializar un repositorio en Git.
## COMANDO: git add
Le estás diciendo a Git que quieres guardar los cambios que hiciste en un archivo o carpeta para que se guarden la próxima vez que hagas una confirmación.
## COMANDO: git commit
Comando para el generar un registro de un cambio. ***[Tipo commmit: descripción de 40 caracteres máximo]***
1. git commit `<file>`
2. git commit -m `<descripción>`
3. git commit file -m `<descripción>`
4. ## COMANDO: git log
Muestra una lista de todos los cambios que se han hecho en el proyecto a lo largo del tiempo.
1. Esto te da una lista de los cambios en una línea para que sea más fácil de leer.: **git log --oneline**
2. Esto te muestra cómo se han unido las diferentes partes del proyecto, como en un gráfico.
: **git log --graph**
## README
El `README` es como una carta de presentación para el proyecto. Está escrito en un formato llamado Markdown para que sea fácil de entender y se vea bien organizado.<br>
[**Tutorial Markdown**](https://tutorialmarkdown.com/sintaxis)
## COMANDO: git branch 
Devuelve todas las ramas que existen.
## COMANDO: git branch nombre_Rama
Crea la rama a partir de la rama en la que nos encontramos, los cambios que ocurren en una rama no afectan a otras hasta utilizar un merge.
## COMANDO: git switch nombre_Rama
Nos permite navegar entre las ramas.
## COMANDO: git merge nombre_Rama
Obtiene los cambios de la rama indicada en el comando y los actualiza en la rama en la que nos encontramos; es como mezclar ingredientes para tener la receta completa en un solo lugar.
## COMANDO: git config
1. --global user.name `<nombreUsuario>`
2. --global user.email `<email>`
3. ## File explorer y las ramas
Los archivos y sus cambios se van a mostrar de acuerdo a la rama en la que nos encontremos, cuando entres a alguna rama algunas veces el archivo no sera el mismo que en otra rama.
## Conflictos
Dos ramas modifican el mismo archivo, entonces Git no sabes que version del archivo implementar.
## Ramas
1. Main/Master.- Es la rama principal.
2. Otras ramas.- Son bifurcaciones de la rama principal, son copias del proyecto pero separada para poder ser trabajadas sin poner en riesgo otras ramas.

![Ramas](Imágenes/Ramas.png)

## Fast forward
Una rama A se fusiona a la rama B incluyendo los commits **(git merge `<rama>`)**.
## No fast forward
Una rama A se fusiona a la rama B integrados los cambios de A en B, pero con la diferencia de que la visualización de la rama A queda separada de la rama B se podria decir una mejor visualizacion **(git merge `<rama>` --no-ff)**
*Tanto si usamos Fast forward como No fast forward solo cambiara la forma en la que visualizaremos el histórico de nuestro repositorio*
## COMANDO: git merge -s ours `<rama>`
Los cambios de la rama A se conservan mientras no hayan conflictos con la rama B, en caso de conflicto se prioriza lo que está en la rama B
## COMANDO: git merge -s theirs `<rama>`
Los cambios de la rama A se conservan mientras no hayan conflictos con la rama B, en caso de conflicto se prioriza lo que está en la rama A
### Ejemplo
![Ours and Theirs](Imágenes/Merge%20ours%20and%20theirs.png)

## COMANDO: git pull-request
Petición para hacer cambios en la rama main.
## GitHub
Es un repositorio en la nube, existen otros como GitLab o Bitbucket.
## COMANDO: git remote -v
Nos permite ver el repositorio remoto al que estamos conectados.
## COMANDO: git remote add origin `<URL>`
Obtenemos acceso al repositorio en la nube. <br>
Origin es el fuente/origen del repositorio en el que trabajaremo en GitHub basicamente es como un sobrenombre.
## COMANDO: git push origin main
Subimos una rama <main> al repositorio origin.
## COMANDO: git clone `<URL>`
Comando para clonar la rama principal de un repositorio pero con **git switch `<nombre_rama>`** podemos ingresar a las otras ramas existentes del repositorio.
## COMANDO: git pull
Comando para agregar una rama a nuestro repositorio local, luego debemos escribir ***git switch `<nombre_rama>`*** para ingresar a la rama y así poder visibilizarla con el **git branch**.
1. **git pull origin `<nombre_rama>`**
2. ## Flujo de Trabajo en equipos
Conjunto de reglas a las cuales se rige un repositorio.
## 1. Basic Workflow
Usualmente se usa individualmente en un proyecto pequeño.

![Basic](Imágenes/Basic.png)

## 2. Feature Branch Workflow
Suele ser usado en trabajos en equipo para proyectos pequeños.

![Feature Branch](Imágenes/Feature%20branch.png)

## 3. Gitflow Workflow
Se utilizan en trabajos en equipo para proyectos más grandes y extensos.

![Gitflow](Imágenes/Gitflow.png)

1. Main.- Es la versión del proyecto, en esta rama se añaden los proyectos ya finalizados y que hayan pasado por el release o hotfix en algunos casos.
2. Hotfix.- Es un parcheo o arreglo inmediato del proyecto. De aquí nacen las versiones 1.2, 2.1.2, etc
3. Release.- Últimos detalles como revisiones, documentación concisa y testeo.
4. Develop.- Desarrollo y documentación de código.
5. Feature.- Ramas de desarrollo pertenecientes a cada integrante del equipo.<br>
**De la rama Main al Develop son únicas**
## 4. Forking Workflow
Consiste en clonar el repositorio y emplear algunos de los anteriores Workflow

![Forking](Imágenes/Forking.png)

## Alias
Sirve para relacionar un comando extenso a un comando elaborado por uno mismo.
- Ejemplo 1: **git config --global alias.co checkout**
- Ejemplo 2: **git config --global alias.last 'log -1 HEAD'**
- Enlistar alias: **git config --list | grep alias**
- Borrar alias: **git config --global --unset alias.`<nombre_Alias>`**
## Stash
Son guardados rápidos y temporales que se hacen en Git, se usan para poder cambiar de rama sin realizar commits ni perjudicar la rama actual.
- Guardar la rama temporalmente: **git stash**
- Ver la lista de stash: **git stash list**
- Recuperar un stash específico: **git stash apply stash@{`<N>`}**
- Recuperar el último stash y lo elimina del stash: **git stash pop**
- Eliminar un stash especifico: **git stash drop stash@{`<N>`}**
- Eliminar todos los stash: **git stash clear**

## Busquedas Grep
Son realmente rápidas, busca a través de cualquier árbol en Git, no solo en el directorio de trabajo.
- Encontrar coincidencias por archivo: **git grep -n `<pattern>`**
- Enumerar coincidencias por archivo: **git grep -c `<pattern>`**