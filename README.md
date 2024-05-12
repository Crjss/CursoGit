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