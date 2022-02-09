<h1 align="center">Hi 👋, I'm Oscar J. Abuawad L.</h1>
<h3 align="center">Tutorial básico de git y github</h3>

## Basic commands

`git init` --inicializa un repositorio en un directorio

`git status` --muestra el estado del repositorio

`git add .` --añade todos los archivos necesarios a la db

`git commit -m "mensaje"` --añade los cambios a la BD del repositorio y -m le agrega un mensaje

`git remote add origin <direccion del repo en github>` --Añade al repositorio local el repositorio en github

`git push -u origin <rama>` --sube los cambios al repositorio en github en la rama <rama>

`git fetch origin` --sincroniza cambios con el repositorio para tener la ultima version 

`git pull origin master` --obtendrá todos los cambios de la rama maestra del control remoto y los fusionará en su local 

`git merge origin/master` --Nosotros podemos hacer lo mismo con este comando

Git Cheat Sheet en español [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============

### Índice
* [Configuración](#configuración)
* [Archivos de Configuración](#archivos-de-configuración)
* [Crear](#crear)
* [Cambios locales](#cambios-locales)
* [Buscar](#buscar)
* [Historial de Commits](#historial-de-commits)
* [Ramas & Etiquetas](#ramas--etiquetas)
* [Actualizar & Publicar](#actualizar--publicar)
* [Fusionar & Rebasar](#fusionar--rebasar)
* [Deshacer](#deshacer)
* [Git Flow](#git-flow)

<hr>

## Configuración

##### Mostrar la cofiguración actual:
```
$ git config --list
```

##### Mostrar la configuración local:
```
$ git config --local --list
```

##### Mostrar la configuración global:
```
$ git config --global --list
```

##### Mostrar la configuración del sistema:
```
$ git config --system --list
```

##### Establecer un nombre que es identificable de crédito cuando se revise el historial de versiones:
```
$ git config --global user.name “[nombre apellido]”
```

##### Establecer una dirección de email que será asociada con cada marca histórica:
```
$ git config --global user.email “[email-válido]”
```

##### Establecer coloreado automático de la línea de comandos de Git para una fácil revisión:
```
$ git config --global color.ui auto
```

##### Establecer el editor global para commits:
```
$ git config --global core.editor vi
```

<hr>

## Archivos de Configuración

##### Archivo de configuración específico del repositorio [--local]:
```
<repo>/.git/config
```

##### Archivo de configuración específico del usuario [--global]:
```
~/.gitconfig
```

##### Archivo de configuración del sistema [--system]:
```
/etc/gitconfig
```

<hr>

## Crear

##### Clonar un repositorio existente:

Existen dos maneras:

Vía SSH

```
$ git clone ssh://usuario@dominio.com/repo.git
```

Vía HTTP

```
$ git clone http://dominio.com/usuario/repo.git
```

##### Crea un nuevo repositorio local:
```
$ git init
```

<hr>

## Cambios Locales

##### Cambios en el directorio de trabajo:
```
$ git status
```

##### Cambios en archivos rastreados:
```
$ git diff
```

##### Agregar todos los cambios actuales al siguiente commit:
```
$ git add .
```

##### Agregar algunos cambios de &lt;archivo&gt; para el siguiente commit:
```
$ git add -p <archivo>
```

##### Realizar un commit de todos los cambios locales en los archivos rastreados:
```
$ git commit -a
```

##### Realizar un commit de los cambios previamente almacenados en el área de pruebas (stage area):
```
$ git commit
```

##### Realizar un commit con un mensaje:
```
$ git commit -m 'aquí el mensaje'
```

##### Realizar un commit saltándose el área de pruebas y agregando un mensaje:
```
$ git commit -am 'aquí el mensaje'
```

##### Realizar un commit a alguna fecha anterior:
```
git commit --date="`date --date='n day ago'`" -am "Mensaje del commit"
```

##### Cambiar último commit:
<em><sub>¡No modificar commits ya publicados!</sub></em>
```
$ git commit -a --amend
```

##### Cambiar fecha del último commit:
```
GIT_COMMITTER_DATE="date" git commit --amend
```

##### Cambiar fecha del autor del último commit:
```
git commit --amend --date="date"
```

##### Mover cambios no confirmados (uncommitted changes) de la rama actual a otra rama:<br>
```
git stash
git checkout branch2
git stash pop
```

##### Restaurar cambios del área de pruebas (stage area) a la rama actual:
```
git stash apply
```

##### Eliminar la última serie de cambios del área de pruebas (stage area):
```
git stash drop
```

<hr>

## Buscar

##### Un texto en todos los archivos del directorio:
```
$ git grep "Hola"
```

##### Un texto en cualquier versión:
```
$ git grep "Hola" v2.5
```

<hr>

## Historial de Commits

##### Mostrar todos los commits, empezando por los más recientes (se mostrará el hash, información sobre el autor, fecha y título del commit):
```
$ git log
```

##### Mostrar todos los commits (sólo se mostrará el hash y el mensaje del commit):
```
$ git log --oneline
```

##### Mostrar todos los commits de un usuario específico:
```
$ git log --author="usuario"
```

##### Mostrar los cambios a través del tiempo de un archivo específico:
```
$ git log -p <archivo>
```

##### Mostrar commmits que están presentes sólamente en remote/branch al lado derecho:
```
$ git log --oneline <origin/master>..<remote/master> --left-right
```

##### Quién cambió, qué y cuándo en &lt;archivo&gt;:
```
$ git blame <archivo>
```

##### Mostrar reference log:
```
$ git reflog show
```

##### Borrar reference log:
```
$ git reflog delete
```

<hr>

## Ramas & Etiquetas

##### Listar todas las ramas locales:
```
$ git branch
```

##### Listar todas las ramas remotas:
```
$ git branch -r
```

##### Cambiar rama HEAD:
```
$ git checkout <rama>
```

##### Crear nueva rama y cambiar a esta:
```
$ git checkout -b <rama>
```

##### Crear nueva rama basada en la rama HEAD actual:
```
$ git branch <nueva-rama>
```

##### Crear nueva rama de seguimiento basada en una rama remota:
```
$ git branch --track <nueva-rama> <rama-remota>
```

##### Eliminar una rama local:
```
$ git branch -d <rama>
```

##### Forzar eliminación de una rama local:
<em><sub>¡Perderás los cambios sin fusionar!</sub></em>
```
$ git branch -D <branch>
```

##### Marcar el commit actual con una etiqueta:
```
$ git tag <tag-name>
```

##### Marcar el commit actual con una etiqueta que incluye un mensaje:
```
$ git tag -a <etiqueta>
```

<hr>

## Actualizar & Publicar

##### Listar todos los remotos configurados actuales:
```
$ git remote -v
```

##### Mostrar información sobre un remoto:
```
$ git remote show <remoto>
```

##### Agregar un nuevo repositorio, nombrado &lt;remoto&gt;:
```
$ git remote add <remoto> <url>
```

##### Quitar el repositorio &lt;remoto&gt; agregado previamente:
```
$ git remote rm <remoto>
```

##### Descargar todos los cambios de &lt;remoto&gt;, pero no integrarlos al HEAD:
```
$ git fetch <remoto>
```

##### Descargar cambios y fusionarlos/integrarlos directamente al HEAD:
```
$ git remote pull <remote> <url>
```

##### Obtener todos los cambios del HEAD al repositorio local:
```
$ git pull origin master
```

##### Obtener todos los cambios del HEAD al repositorio local sin fusionar:
```
git pull --rebase <remote> <branch>
```

##### Publicar cambios locales en un remoto:
```
$ git push remote <remoto> <rama>
```

##### Eliminar una rama en el remoto:
```
$ git push <remoto> :<rama> (desde Git v1.5.0) ó $ git push <remoto> --delete <rama> (desde Git v1.7.0)
```

##### Publicar tus etiquetas:
```
$ git push --tags
```

<hr>

## Fusionar y Rebasar

##### Fusionar <rama> en tu HEAD actual:
```
$ git merge <rama>
```

##### Rabasar tu actual HEAD sobre &lt;rama&gt;:<br>
<em><sub>¡No rebasar commits ya publicados!</sub></em>
```
$ git rebase <rama>
```

##### Aborta un rebase:
```
$ git rebase --abort
```

##### Continuar un rebase después de resolver conflictos:
```
$ git rebase --continue
```

##### Usar tu herramienta de fusión configurada para resolver conflictos:
```
$ git mergetool
```

##### Usar tu editor para manualmente resolver conflictos y (después de resueltos) marcar el archivo como resuelto:
```
$ git add <archivo-resuelto>
```

```
$ git rm <archivo-resuelto>
```

##### Aplastando commits (squashing):
```
$ git rebase -i <commit-just-before-first>
```

Ahora reemplazando esto,

```
pick <commit_id>
pick <commit_id2>
pick <commit_id3>
```

con esto,

```
pick <commit_id>
squash <commit_id2>
squash <commit_id3>
```

<hr>

## Deshacer

##### Descartar todos los cambios locales en tu directorio de trabajo:
```
$ git reset --hard HEAD
```

##### Sacar todos los archivos del área de pruebas (es decir, deshacer el último `git add`):
```
$ git reset HEAD
```

##### Descartar cambios locales de un archivo específico:
```
$ git checkout HEAD <archivo>
```

##### Revertir un commit (produciendo un nuevo commit con los cambios contrarios):
```
$ git revert <commit>
```

##### Reestablecer tu puntero HEAD a un commit anterior y descartar todos los cambios desde entonces:
```
$ git reset --hard <commit>
```

##### Reestablecer tu puntero HEAD al estado actual de una rama remota.
```
$ git reset --hard <remote/branch> es decir, upstream/master, origin/my-feature
```

##### Reestablecer tu puntero HEAD a un commit anterior y preservar todos los cambios en el área de pruebas (stage area):
```
$ git reset <commit>
```

##### Reestablecer tu puntero HEAD a un commit anterior y preservar los cambios locales sin confirmar (uncommitted changes):
```
$ git reset --keep <commit>
```

##### Remover los archivos que fueron accidentalmente agregados al commit antes de ser añadidos al .gitignore:
```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```

<hr>

##  Git-Flow

### Índice
* [Configuración](#configuración)
* [Iniciando](#iniciando)
* [Features (características)](#features__características_)
* [Hacer un lanzamiento](#hacer-un-lanzamiento)
* [Hotfixes (revisiones)](#hotfixes__revisiones_)
* [Comandos](#commandos)

<hr>

### Configuración
###### Necesitas tener Git instalado como prerequisito. Git flow trabaja en OSX, Linux y Windows.

##### OSX Homebrew:
```
$ brew install git-flow
```

##### OSX Macports:
```
$ port install git-flow
```

##### Linux (basado en Debian):
```
$ apt-get install git-flow
```

##### Windows (Cygwin):
###### Necesitas wget y util-linux para instalar git-flow.
```
$ wget -q -O - --no-check-certificate https://github.com/nvie/gitflow/raw/develop/contrib/gitflow-installer.sh | bash
```

<hr>

### Iniciando
###### Git flow necesita ser inicializado con el fin de personalizar la configuración de tu proyecto. Empieza usando git-flow inicializándolo dentro de un repositorio git existente:

##### Inicilizar:
###### Tendrás que responder un par de preguntas acerca de las convenciones de nombramiento de tus ramas. Es recomendable usar los valores por defecto.
```
git flow init
```

<hr>

### Features (características)
###### Desarrolla nuevos features para próximos lanzamientos. Típicamente sólo existen en los repositorios de desarrolladores.

##### Iniciar un nuevo feature:
###### Esta acción crea una nueva rama (feature branch) basada en la rama de desarrollo (develop branch) y cambia a esta.
```
git flow feature start MIFEATURE
```

##### Terminar un feature:
###### Finalizar el desarrollo de un feature. Esta accion realiza lo siguiente:
###### 1) Fusiona MIFEATURE con la rama de desarrollo (develop branch).
###### 2) Elimina la rama del feature (feature branch).
###### 3) Cambia nuevamente a la rama de desarrollo (develop branch).
```
git flow feature finish MIFEATURE
```

##### Publicar un feature:
###### ¿Estás desarrollando un feature colaborativamente? Publica un feature en el servidor remoto, así puede ser usado por otros usuarios.
```
git flow feature publish MIFEATURE
```

##### Obteniendo un feature publicado:
###### Obtener un feature publicado por otro usuario.
```
git flow feature pull origin MIFEATURE
```

##### Rastrear un origin feature:
###### Puedes rastrear un feature en origin usando:
```
git flow feature track MIFEATURE
```

<hr>

### Hacer un lanzamiento
###### Apoya la preparación de un nuevo lanzamiento a producción. Permite la corrección de pequeños bugs y la preparación de metadatos para un lanzamiento.

##### Empezar un lanzamiento:
###### Para empezar un lanzamiento, usa el comando "release" de git flow. Este crea una rama de lanzamiento (release branch) de la rama de desarrollo (develop branch). Opcionalmente puedes sustituir el hash sha-1 de un commit [BASE] para empezar el lanzamiento desde este. El commit debe estar en la rama de desarrollo (develop branch).
```
git flow release start RELEASE [BASE]
```
###### Es aconsejable publicar la rama de lanzamiento (release branch) después de crearla para permitir publicar commits de otros desarrolladores. Hazlo de manera similar a publicar un feature con el comando:
```
git flow release publish RELEASE
```

###### (Puedes rastrear un lanzamiento remoto con el comando: ```git flow release track RELEASE```)

##### Terminando un lanzamiento:
###### Terminando un lanzamiento es uno de los grandes pasos en la ramificación de git. Realiza varias acciones:
###### 1) Fusiona la rama de lanzamiento (release branch) con la rama master.
###### 2) Etiqueta la publicación con su nombre.
###### 3) Vuelve a fusionar la rama de lanzamiento (release branch) en la rama de desarrollo (develop branch).
###### 4) Elimina la rama de lanzamiento (release branch).
```
git flow release finish RELEASE
```
###### No olvides de publicar tus etiquetas con ```git push --tags```

<hr>

### Hotfixes (revisiones)
###### Los hotfixes surgen de la necesidad de actuar inmediatamente ante un estado indeseado en una versión de producción en vivo. Puede ser desramificada de la correspondiente etiqueta en la rama master que marca la versión de producción.

##### Emepezar un hotfix en git flow:
###### Como los otros comandos de git flow, un hotfix es inicializado con:
```
$ git flow hotfix start VERSION [BASENAME]
```

###### El argumento versión marca el nombre de publicación del nuevo hotfix. Opcionalmente puedes especificar un nombre base desde cual empezar.

##### Terminar un hotfix:
###### Al finalizar un hotfix este se fusiona nuevamente con la rama de desarrollo y la rama master. Adicionalmente la fusión master es etiquetada con la versión del hotfix.
```
git flow hotfix finish VERSION
```

<hr>

### Comandos
<p align="center">
	<img alt="Git" src="/img/git-flow-commands.png" height="270" width="460">
</p>

<hr>

### Esquema de git flow
<p align="center">
	<img alt="Git" src="/img/git-flow-commands-without-flow.png">
</p>

<hr>
