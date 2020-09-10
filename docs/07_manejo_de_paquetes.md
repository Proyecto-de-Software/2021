Manejo de paquetes en Python
============================

El manejador de paquetes `pip` tiene como objetivo realizar la instalación de
paquetes externos o librerías que querramos usar en nuestros proyectos.

La herramienta sirve para descargar las mismas del repositorio de código
[`pypi`](https://pypi.org/) donde están publicadas. Aunque se podría configurar
para descargarla de otro repositorio, por ejemplo, uno propio.

Generalmente cuando instalamos la versión de Python que vamos a utilizar ya
tenemos la herramienta `pip` instalada para esa versión. En caso de no ser así
podemos instalarla fácilmenten:

1. Descargar el contenido de [este archivo](https://bootstrap.pypa.io/get-pip.py)
2. Ejecutar `python <archivo_anterior_descargardo>.py`

Guía completa [aquí](https://pip.pypa.io/en/stable/installing/)

## ¿Cómo usar `pip`?

Para instalar una librería con `pip` ejecutamos:

```bash
pip install art
```

Esto va a instalar la ultipa versión. Si queremos alguna versión en particular
ejecutamos:

```bash
pip install art==4.5
```

Deberíamos hacer esto por cada librería que querramos instalar en el sistema.

Una forma práctica para no tener que repetirlo por cada librería que querramos
usar es tener un archivo donde poner toda las librerías que querramos de la
siguiente manera:

```python
# File: requirements.txt
art==4.5
numpy==1.18.1
pandas==1.0.1
```

Ahora podemos ejecutar un comando para instalar todas al mismo tiempo

```bash
pip install -r requirements.txt
```

!!! info "Documentación completa"
    Enlace de la documentación de comandos de pip
    [aquí](https://pip.pypa.io/en/stable/reference/)
