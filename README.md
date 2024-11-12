# Actividad 4ra5. Git (II)

1. [Configuración adicional de GIT](#configuración-adicional-de-git)
2. [Creación repositorio del proyecto](#creación-repositorio-del-proyecto)


## Configuración adicional de GIT
1. Configuramos el editor por defecto con el comando `git config — global core.editor codium`, en mi caso estoy indicando que el editor sea [VSCodium](https://vscodium.com/).
2. Configuramos tambien que nos muestre los mensajes directamente sin necesidad de entrar en el editor al usar los comandos `git diff` o `git log` con el comando `git config — global core.pager`.
3. Utilizamos el comando `git config --help` para comprobar que se ha aplicado la configuración anterior.
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

