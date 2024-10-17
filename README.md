# GitHub Commits Viewer
Este proyecto es una aplicación móvil desarrollada en Flutter que permite visualizar el historial de commits de un repositorio público de GitHub. La aplicación utiliza la GitHub API para obtener y mostrar los commits en una lista.

## Requisitos previos
Antes de instalar y ejecutar el proyecto, asegúrate de tener lo siguiente instalado:

Flutter
Git
HTTP
VS CODE

## Instrucciones para ejecutar

### Enlace con GitHub
1. Primero creamos nuestro proyecto flutter, ya sea con comando flutter create "nombre_del_proyecto" o con >Flutter New Project
2. Crearemos nuestro repositorio en GitHbu
3. Ahora procederemos a enlazar nuestro proyecto con el repositorio en Github tomando como raiz la carpeta main y no master
Usaremos los comandos desde la terminal (GIT) dentro de nuestro proyecto:
git init
git add .
git commit -m "Initial commit"
Ahora conectaremos el repositorio usando: git remote add origin https://github.com/Kikegg97/test_commits_view
Verifica que el enlace se haya agregado correctamente: git remote -v
Configuramos nuestra rama raiz: git branch -M main
Ahora hacemos un pull y luego un push
git pull origin main --rebase
Ahora usamos git push origin main o sino forzamos el push git push -f origin main

Ahora podemos visualizar todo neustro proyecto en Github
Ahora añadiremos todo de nuevo con git add .
Como estabamos en un rebase, debemos continuar, ejecutamos:
git rebase --continue
Luego dentro de este, presionamos Esc y escribimos :wq
Ahora si estaremos dentro de nuestra carpeta main

### Pasos FrontEnd  y BackEnd
Todo cambio que hagamos registramos nuestros commit
Agregamos la dependencia HTTP en el archivo pubspec.yaml usando:  dart pub add http
git add pubspec.yaml
git commit -m "Added HTTP package for API requests"
git push origin main

Ahora primero haremos una interfaz basica en el main.dart
git add lib/main.dart
git commit -m "Created basic Flutter UI layout with AppBar"
git push origin main

Una vez probado y que funciones, mejoramos la interfaz y efectuamos el commit
git add lib/main.dart
git commit -m "Improved UI to display author initials, commit message, and date"
git push origin main

Pondremos un boton de refrescar para ver los commits recien agregados
git add lib/main.dart
git commit -m "Added refresh button to manually update commits"
git push origin main

Crea un nuevo proyecto con el siguiente comando: nest new github-commits-backend
Crear un servicio para obtener los commits de GitHub: 
nest generate service github
nest generate controller github

Controlador para servir los commits donde haremos enlace el backend con la API de github
En src/github/commits.controller.ts, añade un endpoint que llame al servicio GithubService

Inicializamos este controlador desde app.module.ts

Y posteriormente llamaremos este controlador desde nuestro main, donde ajustaremos segun la direccion IP local o la direccion IP del emulador que es 10.0.2.2. Hay que proabr con cual sirve en nuestra solucion.
