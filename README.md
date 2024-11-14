# Actividad 4ra5. Git (II)

1. [Configuración adicional de GIT](#configuración-adicional-de-git)
2. [Creación repositorio del proyecto](#creación-repositorio-del-proyecto)
3. [Ignorar ficheros con gitignore](#ignorar-ficheros-con-gitignore)
4. [Trabajo con Git](#trabajo-con-git)
5. [Servidor web local](#servidor-web-local)
6. [Más cambios con Git](#más-cambios-con-git)


## Configuración adicional de GIT
1. Configuramos el editor por defecto con el comando `git config --global core.editor codium`, en mi caso estoy indicando que el editor sea [VSCodium](https://vscodium.com/).
2. Configuramos tambien que nos muestre los mensajes directamente sin necesidad de entrar en el editor al usar los comandos `git diff` o `git log` con el comando `git config --global core.pager`.
3. Utilizamos el comando `git config -l` para comprobar que se ha aplicado la configuración anterior.
![Git config list](images/git-config-list.png)
4. Podemos ajustar los colores de diversos datos con los siguientes comandos:
```
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
```

## Creación repositorio del proyecto
En nuestro equipo ejecutamos `git init` en la carpeta donde estamos desarollando este manual. Y creamos el primer coomit.
Accedemos a [GitHub](#https://github.com) y creamos un nuevo repositorio público con el nombre PPS-Unidad0Actividad4-AdrianCurtoSanchez.

![New repository](images/new-repository.png)

Copiamos y pegamos en la terminal los comandos de agregar el repositorio ya existente.
![New repository commands](images/new-repository-commands.png)
```
git remote add origin git@github.com:Acurtos01/PPS-Unidad0Actividad4-AdrianCurtoSanchez.git
git branch -M main
git push -u origin main
```
![New repository commands execution](images/new-repository-commands-execution.png)

## Ignorar ficheros con gitignore
Cremos el directorio *excluided* y el fichero excluido.txt.

![Excluded directory and file](images/excluded-directory-file.png)

Como se puede apreciar en la captura anterior git nos está indicando que hay dos nuevos elementos. Ahora creamos el fichero .gitignore e introducimos lo siguiente dentro de el para evitar que git continue realizando el siguimiento del direcotrio y el fichero creado anteriormente:
```
/excluded
*.txt
```
Ahora podemos observar que han sido excluidos del seguimiento.

![Created gitignore](images/created-gitignore.png)


## Trabajo con Git

Creamos un fichero en nuestro proyecto con el nombre index.html, el cual contendrá el siguiente código:
```
<H1>Hola $USER¡¡¡ ¿Qué tal te encuentras?</H1>
```

Una vez creado el fichero con su contenido podemos obtener una pequeña ayuda de git con el comando `git status -s`el cual con el parámetro *-s* nos devolverá una salida abrebiada.

![Git status short](images/git-status-short.png)

En la salida anterior podemos observar que el fichero README.md ha sido modificado e index.html se encuentra en estado sin seguimiento.

Para crear un commit con estos cambios ejecutaremos el comando `git commit -am "mensaje del commit"`, el parámetro *a* indica que se agregen todos los ficheros rastreados y el parámetro m permite especificar el mensaje del commit.

![Git commit -am](images/git-commit-am.png)

Volvemos a ejecutar el comando `git status -s` y esta vez no nosmuestra ningún fichero, podemos estar seguros de que nuestros ambios están guadados y podemos realizar la subida al repositorio remoto con `git push`.


## Servidor web local

Para visualizar los cambios en el fichero index.html en local podemos ejecutar un servicio php con el comando `php -S 0:8080`en el directior actual del proyecto.

![Execute PHP server](images/execute-php-server.png)

Ahora en el navegador podemos acceder a http://localhost:8080 y podremos observar el contenido de index.html.

![localhost index](images/localhost-index.png)


## Más cambios con Git

Creamos una copia de index.html con nombre index.html.save.

![Created index.html.save](images/created-index.html.save.png)

Ahora que tenemos una copia implemetaremos cambios en el fichero index.html y al refrescar la página en el navegador veremos los cabios aplicados.

![Changes index.html](images/changes-index.html.png)

Ahora si verificamos el estado del proyecto con `git status` veremos los ficheros nuevos que aún no estan en seguimiento y los ficheros con cambios. Tambien nos da sugerencias de que hacer con esos ficheros.

![git status](images/git-status.png)

Con el comando `git diff`podemos revisar los ficheros con cambios en el proyecto.

![git diff](images/git-diff.png)

Para volver a la versión anterior de index.html empleamos el comando `git restore index.html`, tras este cambio si refrescamos el navegador veremos el fichero a vuelto al estado anterior.

![localhost-index-restore](images/localhost-index-restore.png)

Otra alternativa al paso anerior es el empleo del comando `git mv index.html.save index.html` idicamos que el contenido de index.html.save pase a index.html.

![git mv fail](images/git-mv-fail.png)

Para poder ejecutar el comando anerior el ficheros origen debe estar bajo seguimiento, sino nos dará un error como se aprecia en la captura anterior. Añadimos el fichero index.html.save al seguimiento y borramos el fichero index.html ya que el comando `git mv` lo que hace el mover ficheros o copiarlos.



