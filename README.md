<h1 align="center">Hi 馃憢, I'm Oscar J. Abuawad L.</h1>
<h3 align="center">Tutorial b谩sico de git y github</h3>

## Basic commands

`git init` --inicializa un repositorio en un directorio

`git status` --muestra el estado del repositorio

`git add .` --a帽ade todos los archivos necesarios a la db

`git commit -m "mensaje"` --a帽ade los cambios a la BD del repositorio y -m le agrega un mensaje

`git remote add origin <direccion del repo en github>` --A帽ade al repositorio local el repositorio en github

`git push -u origin <rama>` --sube los cambios al repositorio en github en la rama <rama>

`git fetch origin` --sincroniza cambios con el repositorio para tener la ultima version 

`git pull origin master` --obtendr谩 todos los cambios de la rama maestra del control remoto y los fusionar谩 en su local 

`git merge origin/master` --Nosotros podemos hacer lo mismo con este comando

Git Cheat Sheet en espa帽ol [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============

### 脥ndice
* [Configuraci贸n](#configuraci贸n)
* [Archivos de Configuraci贸n](#archivos-de-configuraci贸n)
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

## Configuraci贸n

##### Mostrar la cofiguraci贸n actual:
```
$ git config --list
```

##### Mostrar la configuraci贸n local:
```
$ git config --local --list
```

##### Mostrar la configuraci贸n global:
```
$ git config --global --list
```

##### Mostrar la configuraci贸n del sistema:
```
$ git config --system --list
```

##### Establecer un nombre que es identificable de cr茅dito cuando se revise el historial de versiones:
```
$ git config --global user.name 鈥淸nombre apellido]鈥?
```

##### Establecer una direcci贸n de email que ser谩 asociada con cada marca hist贸rica:
```
$ git config --global user.email 鈥淸email-v谩lido]鈥?
```

##### Establecer coloreado autom谩tico de la l铆nea de comandos de Git para una f谩cil revisi贸n:
```
$ git config --global color.ui auto
```

##### Establecer el editor global para commits:
```
$ git config --global core.editor vi
```

<hr>

## Archivos de Configuraci贸n

##### Archivo de configuraci贸n espec铆fico del repositorio [--local]:
```
<repo>/.git/config
```

##### Archivo de configuraci贸n espec铆fico del usuario [--global]:
```
~/.gitconfig
```

##### Archivo de configuraci贸n del sistema [--system]:
```
/etc/gitconfig
```

<hr>

## Crear

##### Clonar un repositorio existente:

Existen dos maneras:

V铆a SSH

```
$ git clone ssh://usuario@dominio.com/repo.git
```

V铆a HTTP

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

##### Realizar un commit de los cambios previamente almacenados en el 谩rea de pruebas (stage area):
```
$ git commit
```

##### Realizar un commit con un mensaje:
```
$ git commit -m 'aqu铆 el mensaje'
```

##### Realizar un commit salt谩ndose el 谩rea de pruebas y agregando un mensaje:
```
$ git commit -am 'aqu铆 el mensaje'
```

##### Realizar un commit a alguna fecha anterior:
```
git commit --date="`date --date='n day ago'`" -am "Mensaje del commit"
```

##### Cambiar 煤ltimo commit:
<em><sub>隆No modificar commits ya publicados!</sub></em>
```
$ git commit -a --amend
```

##### Cambiar fecha del 煤ltimo commit:
```
GIT_COMMITTER_DATE="date" git commit --amend
```

##### Cambiar fecha del autor del 煤ltimo commit:
```
git commit --amend --date="date"
```

##### Mover cambios no confirmados (uncommitted changes) de la rama actual a otra rama:<br>
```
git stash
git checkout branch2
git stash pop
```

##### Restaurar cambios del 谩rea de pruebas (stage area) a la rama actual:
```
git stash apply
```

##### Eliminar la 煤ltima serie de cambios del 谩rea de pruebas (stage area):
```
git stash drop
```

<hr>

## Buscar

##### Un texto en todos los archivos del directorio:
```
$ git grep "Hola"
```

##### Un texto en cualquier versi贸n:
```
$ git grep "Hola" v2.5
```

<hr>

## Historial de Commits

##### Mostrar todos los commits, empezando por los m谩s recientes (se mostrar谩 el hash, informaci贸n sobre el autor, fecha y t铆tulo del commit):
```
$ git log
```

##### Mostrar todos los commits (s贸lo se mostrar谩 el hash y el mensaje del commit):
```
$ git log --oneline
```

##### Mostrar todos los commits de un usuario espec铆fico:
```
$ git log --author="usuario"
```

##### Mostrar los cambios a trav茅s del tiempo de un archivo espec铆fico:
```
$ git log -p <archivo>
```

##### Mostrar commmits que est谩n presentes s贸lamente en remote/branch al lado derecho:
```
$ git log --oneline <origin/master>..<remote/master> --left-right
```

##### Qui茅n cambi贸, qu茅 y cu谩ndo en &lt;archivo&gt;:
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

##### Forzar eliminaci贸n de una rama local:
<em><sub>隆Perder谩s los cambios sin fusionar!</sub></em>
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

##### Mostrar informaci贸n sobre un remoto:
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
$ git push <remoto> :<rama> (desde Git v1.5.0) 贸 $ git push <remoto> --delete <rama> (desde Git v1.7.0)
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
<em><sub>隆No rebasar commits ya publicados!</sub></em>
```
$ git rebase <rama>
```

##### Aborta un rebase:
```
$ git rebase --abort
```

##### Continuar un rebase despu茅s de resolver conflictos:
```
$ git rebase --continue
```

##### Usar tu herramienta de fusi贸n configurada para resolver conflictos:
```
$ git mergetool
```

##### Usar tu editor para manualmente resolver conflictos y (despu茅s de resueltos) marcar el archivo como resuelto:
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

##### Sacar todos los archivos del 谩rea de pruebas (es decir, deshacer el 煤ltimo `git add`):
```
$ git reset HEAD
```

##### Descartar cambios locales de un archivo espec铆fico:
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

##### Reestablecer tu puntero HEAD a un commit anterior y preservar todos los cambios en el 谩rea de pruebas (stage area):
```
$ git reset <commit>
```

##### Reestablecer tu puntero HEAD a un commit anterior y preservar los cambios locales sin confirmar (uncommitted changes):
```
$ git reset --keep <commit>
```

##### Remover los archivos que fueron accidentalmente agregados al commit antes de ser a帽adidos al .gitignore:
```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```

<hr>

##  Git-Flow

### 脥ndice
* [Configuraci贸n](#configuraci贸n)
* [Iniciando](#iniciando)
* [Features (caracter铆sticas)](#features__caracter铆sticas_)
* [Hacer un lanzamiento](#hacer-un-lanzamiento)
* [Hotfixes (revisiones)](#hotfixes__revisiones_)
* [Comandos](#commandos)

<hr>

### Configuraci贸n
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
###### Git flow necesita ser inicializado con el fin de personalizar la configuraci贸n de tu proyecto. Empieza usando git-flow inicializ谩ndolo dentro de un repositorio git existente:

##### Inicilizar:
###### Tendr谩s que responder un par de preguntas acerca de las convenciones de nombramiento de tus ramas. Es recomendable usar los valores por defecto.
```
git flow init
```

<hr>

### Features (caracter铆sticas)
###### Desarrolla nuevos features para pr贸ximos lanzamientos. T铆picamente s贸lo existen en los repositorios de desarrolladores.

##### Iniciar un nuevo feature:
###### Esta acci贸n crea una nueva rama (feature branch) basada en la rama de desarrollo (develop branch) y cambia a esta.
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
###### 驴Est谩s desarrollando un feature colaborativamente? Publica un feature en el servidor remoto, as铆 puede ser usado por otros usuarios.
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
###### Apoya la preparaci贸n de un nuevo lanzamiento a producci贸n. Permite la correcci贸n de peque帽os bugs y la preparaci贸n de metadatos para un lanzamiento.

##### Empezar un lanzamiento:
###### Para empezar un lanzamiento, usa el comando "release" de git flow. Este crea una rama de lanzamiento (release branch) de la rama de desarrollo (develop branch). Opcionalmente puedes sustituir el hash sha-1 de un commit [BASE] para empezar el lanzamiento desde este. El commit debe estar en la rama de desarrollo (develop branch).
```
git flow release start RELEASE [BASE]
```
###### Es aconsejable publicar la rama de lanzamiento (release branch) despu茅s de crearla para permitir publicar commits de otros desarrolladores. Hazlo de manera similar a publicar un feature con el comando:
```
git flow release publish RELEASE
```

###### (Puedes rastrear un lanzamiento remoto con el comando: ```git flow release track RELEASE```)

##### Terminando un lanzamiento:
###### Terminando un lanzamiento es uno de los grandes pasos en la ramificaci贸n de git. Realiza varias acciones:
###### 1) Fusiona la rama de lanzamiento (release branch) con la rama master.
###### 2) Etiqueta la publicaci贸n con su nombre.
###### 3) Vuelve a fusionar la rama de lanzamiento (release branch) en la rama de desarrollo (develop branch).
###### 4) Elimina la rama de lanzamiento (release branch).
```
git flow release finish RELEASE
```
###### No olvides de publicar tus etiquetas con ```git push --tags```

<hr>

### Hotfixes (revisiones)
###### Los hotfixes surgen de la necesidad de actuar inmediatamente ante un estado indeseado en una versi贸n de producci贸n en vivo. Puede ser desramificada de la correspondiente etiqueta en la rama master que marca la versi贸n de producci贸n.

##### Emepezar un hotfix en git flow:
###### Como los otros comandos de git flow, un hotfix es inicializado con:
```
$ git flow hotfix start VERSION [BASENAME]
```

###### El argumento versi贸n marca el nombre de publicaci贸n del nuevo hotfix. Opcionalmente puedes especificar un nombre base desde cual empezar.

##### Terminar un hotfix:
###### Al finalizar un hotfix este se fusiona nuevamente con la rama de desarrollo y la rama master. Adicionalmente la fusi贸n master es etiquetada con la versi贸n del hotfix.
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
