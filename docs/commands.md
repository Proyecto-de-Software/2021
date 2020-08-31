# Comandos

En esta guía vamos a dejar una lista de comandos de consola que posiblemente
van a utilizar.
Los comando son específicamente de Linux, pero los pueden usar en `GitBash` si
trabajan con Windows.

## Comandos de consola

```bash
pwd              # Imprime el directorio actual.

ls               # Lista todos los archivos y directorios del directorio actual.

ls -a            # Igual que el anterior pero unlcuye los ocultos.

mkdir dirname    # Crea un nuevo directorio en el actual llamado "dirname".

touch filename   # Crea un archivo en el directorio actual llamado "filename".

cd code/python   # Se nueve al directorio "code/python".
```

## Comandos de git

```bash
git status                    # Muestra el estado de los archivos respecto al repositorio.

git add <filename>            # Agrega el archivo filename al versionado de git.

git add .                     # Agrega todos los archivos que sufieron una modificación el versionado.

git commit -m <mensaje>       # Genera un commit con todos los archivos que fueron modificados y gregados a git. Documenta el commit con el mensaje que escribamos.

git checkout -b <branch_name> # Genera una nueva rama localmente con el nombre <branch_name>. Y se mueve a esa rama.

git checkout <branch_name>    # Se mueve a la rama <branch_name> local y si no existe la crea y se mueve.

git push origin <branch_name> # Se suben los commits locales a la rama <branch_name> ubicada en el remote con nombre origin.

git pull origin <branch_name> # Descarga los commits que estén en la rama del remote origin para la rama <branch_name>.
```
