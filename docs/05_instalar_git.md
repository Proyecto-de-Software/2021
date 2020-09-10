Guía de Git
===========

En la explicación práctica hablamos sobre los conceptos de git. Aquí están las
[diapositivas](https://docs.google.com/presentation/d/1pQyjBfV_tz7M2PCS3nvcnHsRaJmJaWhbYeIzzddTfVA/edit?usp=sharing).

## Instalación

!!! warning
    Tener en cuenta que esta guía de instalación de git no hace falta si se
    utilza la máquina virtual que entregamos en la cátedra para trabajar dado
    que tiene todo instalado.
    La máquina vistual la pueden descargar desde [aquí](https://catedras.info.unlp.edu.ar/mod/url/view.php?id=24366)

### En Debian-based

```bash
sudo apt update
sudo apt upgrade
sudo apt install git
```

### En Red Hat-based

```bash
sudo yum upgrade
sudo yum install git
```

### En MacOS

```bash
brew install git
```

### En Windows

Descargar en instalar de [gitforwindows](https://gitforwindows.org/) o de
[git-scm](https://git-scm.com/download/win). Tener en cuenta que en la cátedra
vamos a utilizar `GitBash` por lo cual deben asegurarse que se instale.

## Crear una cuenta de Github

Para crear una cuenta tienen que entrar a la
[web de Github](https://github.com/) y regitrarse (Sing up).

## ¿Cómo usar Git?

Vamos a ver dos formas para comenzar a trabajar con `Git`:

- Creando un repositorio desde cero y agregando los archivos iniciales.
- Descargando un proyecto ya creado y modificarlo.

### Configurar información en Git

En git cuando se va a realizar una operación para generar una nueva versión del
código es necesario contar con información de usuario. Por esto es necesario que
configuremos lo siguiente:

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

Para ver la configuración:

```bash
git config --list
```
