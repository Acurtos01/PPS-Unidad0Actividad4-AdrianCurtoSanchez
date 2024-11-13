# Actividad 4ra5. Git (II)

1. [Configuración adicional de GIT](#configuración-adicional-de-git)
2. [Creación repositorio del proyecto](#creación-repositorio-del-proyecto)
3. [Ignorar ficheros con gitignore](#ignorar-ficheros-con-gitignore)
4. [Trabajo con Git](#trabajo-con-git)


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