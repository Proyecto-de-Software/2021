# Aplicación Base

En la siguiente guía se va a explicar sobre la aplicación base brindada por la
cátedra.

## Versiones en el Server

- Python: 3.6.x
- Mysql: 10.1.44-MariaDB

## Dependencias

Las dependencias del proyecto se encuentran en el archivo `requirements.txt`:

- Flask v1.0.2       -> web framework
- PyMysql v0.9.2     -> conexión a la base
- Flask-Session v0.3 -> sesiones almacenadas en el servidor

Cuando vayan agregando nuevas dependencias con el manejador de paquetes de python (pip), es necesario que se vayan agregando en archivo para que luego  sus compañeros/as o en producción puedan instalarse las mismas. Se pueden ingresar editando el archivo y guardándolo `'paquete'=='numero de versión'` como por ejemplo  `Flask==1.0.2`. Para más ejemplos revisar el archivo `requirements.txt` en la aplicación template.

## Archivos y directorios importantes

En el raíz de nuestra template van a encontrar los siguientes archivos y
directorios:

## Directorio raíz

```bash
$ tree -L 1
.
├── app              # directorio principal de código.
├── config.py        # módulo de configuración de la aplicación.
├── db               # directorio con dump inicial de la base de datos.
├── README.md
├── requirements.txt # listado de dependencias.
└── run.py           # entry point.

```

## App

```bash
tree -L 2
.
├── app
│   ├── db.py        # módulo de conexión con la base de datos.
│   ├── helpers      # directorio con funciones auxiliares.
│   ├── __init__.py  # módulo principal.
│   ├── models       # directorio con los modelos (Models).
│   ├── resources    # directorio de los controladores (Controllers).
│   ├── static       # directorio de archivos estáticos.
│   └── templates    # directorio de templates (Views).
├── config.py
├── db
│   └── schema.sql
├── README.md
├── requirements.txt
└── run.py
```

### Helpers

Es el directorio que tiene funciones auxiliares de la aplicación. Generalmente
aquí se encuentra el código que no son parte principal del negocio de la
aplicación pero que se usan en distintas partes del código.

En este caso se pueden ver funciones para el manejo de los errores dentro del
archivo `handler.py` y en `auth.py` tenemos una función para la verificación
de sesión.

### Models

Aquí se encuentra el código referido a la lógica de aplicación concreta. En
general son lo modelos que interactúan con la base de datos y realizan lógica de
negocio.

### Resources

Este directorio tiene los controladores de la aplicación. Los controladores tiene
lógica de la aplicación relacionada con la web. Hace de enlace entre la lógica
de aplicación y la de generación de las vistas. En el subdirectorio `/api` se
encuentran los controladores que devuelven los recursos en formato `json`.

### Static

Aquí se colocan los archivos estáticos y que queremos que puedan ser accedidos
públicamente en nuestra aplicación, como pueden ser hojas de estilo, scripts js
e imágenes.

### Templates

Directorio de los archivos de template de Jinja2. En general se suele crear
un subdirectorio por cada uno de los controladores creados en `resources`.
Seria como las vistas en el modelo MVC.

### Archivo `__init__.py`

Este es el archivo principal de la aplicación que la inicializa y la configura.
En las misma se encuentra una función llamada `create_app` que realiza toda
la configuración:

- Crea la aplicación `flask`.
- Levanta la configuración desde el módulo `config.py` según el `environment`.
- Configura las sesiones, la base de datos y el motor de templates.
- Configura todas las rutas de la aplicación.
- Se registran los manejadores en caso de error.

## Configuración

El módulo de configuración se encuentra en el archivo `config.py`. El mismo
contiene una clase para cada uno de los entornos de ejecución de la aplicación o
`enviroments`.

En la clase `DevelopmentConfig` se debe configurar los parámetros para la
ejecución local de cada desarrollador. La clase está preparada para que cada
desarrollador agregue en variables de entorno los valores particulares de cada
entorno local.

En `ProductionConfig` se colocan los valores para ejecutar la aplicación
en el entorno del server remoto. También esta preparada para tomar los valores
de variables de entorno, pero en este caso se **debe agregar como valores por
default los datos que se les otorgaron de la base**. Esto último es muy
importante dado que en el servidor no se encuentran a agregadas las variables
de entorno.

## Ejecución

La ejecución de la aplicación se realiza desde el archivo `run.py` que instancia
la aplicación y la ejecuta.

```python
from app import create_app

if __name__ == "__main__":
    app = create_app()
    app.run()
```

Es necesario para la correcta ejecución configurar la variable de entorno
`FLASK_ENV` que se toma como parámetro para realizar la carga de la
configuración de nuestra aplicación.
Para ejecutar el ambiente local como ambiente de desarrollo la manera seria la siguiente: `FLASK_ENV=development python run.py` 

## ¿Cómo usar el template?

- Descargar del repositorio el último tag.
- Copiar los archivos de la aplicacion template a dentro del respositorio de su proyecto (si tienen visibles los archivos ocultos, no hay que copiar el directorio `.git`).
- Cargar el archivo `db/schema.sql` en su base de datos local. Para eso pueden utilizar un cliente de base de datos como por ejemplo: `phpMyAdmin` o `mysql workbench` o la misma command line de mysql `mysql -h "host" -u "user" -p "password" "database" < db/schema.sql`. Es importante cargar este archivo sino la aplicacion no funcionara.
- Configurar correctamente la clase `DevelopmentConfig` con los valores del entorno local del proyecto.
- Crear un entorno virtual dentro de nuestro proyecto es necesario ejecutar lo siguiente:
```bash
virtualenv venv
```
- Activar nuestro entorno virtual:
```bash
. venv/bin/activate
```
- Instalar los paquetes de nuestra aplicación:
```bash
pip install -r requirements.txt
```
- Para ejecutar la aplicación indicando el entorno:
```bash
FLASK_ENV=development python run.py
```
```bash
 * Serving Flask app "app" (lazy loading)
 * Environment: development
 * Debug mode: on
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 112-188-961
```
El proyecto queda ejecutandose en el puerto 5000, en un navegador acceder a http://localhost:5000 
