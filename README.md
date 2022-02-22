# Despliege de una aplicación de REACT en AWS

## Prerrequisitos

[Descargar e instalar Node.JS](https://nodejs.org/en/download/)  
Al instalar node se instala NPM. Si ya lo tienes instalado confirma que la versió es arriba de su versión 5.2.0

[Instalar Git en la máquina local](https://github.com/git-guides/install-git). Se tiene que tener instalado Git. Se recomienda instalar una consola de comandos como [Git Bash](https://www.educative.io/edpresso/how-to-install-git-bash-in-windows)

[Tener una cuenta de GitHub](https://github.com/). Para descargar el código del ejemplo se necesita tener una cuenta en GitHub.


## Crear una aplicación REACT - Hello World

En la consola de comandos, ejecutar el siguiente comando. El proceso tardará unos minutos en descargar e instalar todo lo necesario.

`npx create-react-app simplereactapp`

## Ejecutar la aplicación 

Ir al directorio simplereactapp:

`cd simplereactapp`

Correr la aplicación con el siguiente comando:

`npm start`

Enseguida se abrirá tú navegador en el siguiente link (host):  
[http://localhost:3000/](http://localhost:3000/)

![Aplicación React Desplegada Correctamente](/img/reac_app_desplegada.png)

## Subir la aplicación a GitHub

Se recomienda subir el código creado en el paso anterior a su GitHub para poder integrarlo con el servicio de AWS, en el paso siguiente. El alcance de este tutorial no cubré la explicación de como subir el código al repositorio.

En caso de que se queira omitir este paso, se puede utilizar el siguiente url: 
https://github.com/java-in-action/simplereactapp.git en el siguiente paso.

Nota: Git dejó de usar password recientemente para subir cambios, es muy probable que tengas que crear un Personal AccessToken para subir tus cambios. Esta opción se encuentra en Configuración o Settings > Developer settings > Personal Access Token.


### Desplegar la aplicación React en AWS Amplify

1) Iniciar sesión en [AWS Console](https://aws.amazon.com/es/)  
2) Buscar el servicio **AWS Amplify**  
![AWS Amplify>Todas las aplicaciones](/img/aws_amplify.jpg)  
3) Expandir el menú y dar clic en **Todas las aplicaciones**  
![AWS Amplify>Todas las aplicaciones](/img/todas_las_aplicaciones.jpg)  
4) clic en **Nueva aplicación>>Alojar aplicación web**  
![AWS Amplify>Todas las aplicaciones](/img/alojar_aplicacion.jpg)
5) Seleccionar la opción de **GitHub** y clic en **Continuar**  
![AWS Amplify>Todas las aplicaciones](/img/opcion_git_hub.jpg)
6) Establecer y autorizar la conexión con el repositorio de GitHub
    6.1) Clic en **Authorize aws-amplify-console**
    6.2)Introducir las credenciales del repositorio requeridas
7) Seleccionar el repositorio donde desplegaron su código, Ejemplo: **java-in-action/simplereactapp** 
![Seleccionar Repositorio](/img/seleccionar_repo.jpg)
8) Aceptar los valores por defecto y clic en **Siguiente**
9) Dar clic en **Guardar e implementar**
![Guardar e Implementar](/img/guardar_implementar.jpg)
Nota: El proceso tardara unos minutos. Esperar a que los siguientes pasos cambien verde: Aprovisionar, Compilar, Implementar y Verificar.  
Estado inicial:
![Paso inicial, aprovisionar](/img/paso_aprovisionar.jpg)  
Estafo final:
![Paso finar, verificar](/img/paso_fina_verificar.jpg)

10) Identificar la url donde se desplego la aplicación (caudro rojo) y abrirla, ejemplo: https://main.d2de214va3s2xg.amplifyapp.com/

### Lanzar el proceso de integración continua
1) Hacer un cambio al archivo **src/App.js**.
2) Subir el cambio al repositorio con consola, plugin de IDE o directo en GitHub.
Ejemplo:
`git add .`  
`git commit -m"Cambio que lanza el proceso de despliege en Amplify"`  
`git push origin main`
3) Ir a la consola de Amplify y observar el "Pipeline" la línea de producción.
4) Esperar que cada paso se complete (en verde) e refrescar la url de despliege Ej. https://main.d2de214va3s2xg.amplifyapp.com/, para comprobar que el cambio se ha desplegado correctamente.


## Conclusión
Este tutorial enseña como desplegar una aplicación de front-end hecha en react en un servicio de AWS Amplify. El reto esta en configurar el repositorio de gitHub con AWS Amplify. 

Lo interesante de este simple ejercicio, es entender como AWS nos ofrece un servicio que automatiza todo el proceso de despliege e integra un proveedor de repositorio de código (GitHub). 

### Referencias

[Download Node.Js](https://nodejs.org/en/download/)  
[Downloading and installing Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
[Install Git](https://github.com/git-guides/install-git)  
[How to install Git Bash in Windows](https://www.educative.io/edpresso/how-to-install-git-bash-in-windows)  
[AWS Amplify](https://aws.amazon.com/es/amplify/)  
[What are the differences between npm and npx ?](https://www.geeksforgeeks.org/what-are-the-differences-between-npm-and-npx/#:~:text=NPX%3A%20The%20npx%20stands%20for,without%20even%20installing%20that%20package.)  
[Pushing changes to GitHub](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github)





