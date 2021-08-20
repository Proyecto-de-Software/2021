# Comandos

En esta guía vamos a dejar una lista de comandos de consola que posiblemente
van a utilizar.
Los comando son específicamente de Linux, pero los pueden usar en `GitBash` si
trabajan con Windows.

## Comandos de consola

```bash
# Imprimir el directorio actual.
pwd

# Listar todos los archivos y directorios del directorio actual.
ls

# Igual que el anterior pero incluye los archivos y directorios ocultos.
ls -a

# Crear un nuevo directorio en el actual llamado "dirname".
mkdir dirname

# Crear un archivo en el directorio actual llamado "filename".
touch filename

# Moverse al directorio "code/python".
cd code/python
```

## Comandos de git

```bash
# Mostrar el estado de los archivos respecto al repositorio.
git status

# Agregar el archivo filename al versionado de git.
git add <filename>

# Agregar todos los archivos que sufieron una modificación al versionado.
git add .

# Generar un commit con todos los archivos que fueron modificados y agregados a
# git. Documenta el commit con el mensaje que escribamos.
git commit -m <mensaje>

# Generar una nueva rama localmente con el nombre <branch_name>. Y moverse a
# esa rama.
git checkout -b <branch_name>

# Moverse a la rama <branch_name> local y si no existe la crea y se mueve.
git checkout <branch_name>

# Subir los cambios en commits locales a la rama <branch_name> ubicada en el
# remote con nombre origin.
git push origin <branch_name>

# Descargar cambios en commits que estén en la rama del remote origin para la
# rama <branch_name>.
git pull origin <branch_name>

# Fusionar la rama <branch_name> dentro de la rama actual.
git merge <branch_name>
```
