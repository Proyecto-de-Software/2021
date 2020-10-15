# Guía de estilos

Las guías de estilo ayudan a los equipos de desarrollo a escribir código
consistente simplificando su entendimiento a todos/as los/as miembros del
equipo.

Python define en **PEP8** como guía de estilos base y en **PEP257** la convención
para Docstrings. Teniendo esta referencia vamos a mencionar las normas mas
importantes que esperamos que traten de cumplir en el trabajo.

Antes de comenzar a nombrarlas es necesario decir de una regla base a todas las
siguientes a la hora de desarrollar una aplicación en equipo: **ser
consistentes**. ¿Qué quiere decir esto? que **todos los miembros sigan las mismas
reglas para el estilo de escritura del código**.

## Generales:

- Uso de 4 espacios en lugar de tabs. Esto puede ser configurado en su editor
- 120 es el máximo de caracteres por línea. Preferentemente 80
- Dejar 2 líneas en blanco entre clases y funciones
- 1 línea en blanco dentro de la clases entre los métodos de la misma
- No dejar líneas en blanco luego de la línea `def`
- No dejar espacios dentro de los paréntesis, corchetes y las llaves
```python
  # bien
  spam(ham[1], {eggs: 2}, [])

  # mal
  spam( ham[ 1 ], { eggs: 2 }, )
```
- Rodear los operadores con un espacio en blanco de ambos lados
```python
  # bien
  x == 1

  # mal
  x<1
```
- No usar espacios en blanco alrededor del `=` cuando se pasa un `keyword
  argument` o se define un valor por defecto en una función
```python
  # bien
  def function_name(keyword_argument=value):
      pass

  function_name(keyword_argument=1)

  # mal
  def function_name(keyword_argument = value):
      pass

  function_name(keyword_argument = 1)
```
- Usar líneas en blanco para la separación de lógica dentro de las
  funciones/métodos siempre que esté justificado
- Mover los argumentos de una función de una nueva línea con indentación si no
  entran todos en la primer línea
```python
  # bien
  def long_function_name(var_one, var_two, var_three,
          var_four):
      print(var_one)

  # bien
  def long_function_name(
      var_one,
      var_two,
      var_three,
      var_four
  ):
      print(var_one)
```
- Mover las condiciones a nuevas líneas si no entran en el máximo determinado.
Esto te ayudará a entender la condición mirando de arriba hacia abajo.
```python
  # bien
  if (this_is_one_thing
      and that_is_another_thing
      or that_is_third_thing
      or that_is_yet_another_thing
      and one_more_thing
  ):
      do_something()
```
- Usar Strings multilíneas sin `\\`.
```python
  raise AttributeError(
      'Here is a multiline error message '
      'shortened for clarity.'
  )
```
- Use argumentos nombrados para aumentar la legibilidad.
```python
  # bien
  urlget('[http://google.com](http://google.com/)', timeout=20)

  # mal
  urlget('[http://google.com](http://google.com/)', 20)
```
- Nunca termines tus líneas con punto y coma y no las uses para tener dos
  sentencias en la misma línea.
- El encadenamiento de métodos debe ser separado en múltiples líneas para mejor
  legibilidad
```python
  (df.write \
    .format('jdbc')
    .option('url', 'jdbc:postgresql:dbserver')
    .option('dbtable', 'schema.tablename')
    .option('user', 'username')
    .option('password', 'password')
    .save()
  )
```
- Siempre comience el bloque de código en una nueva línea
```python
  # bien
  if flag:
      return None

  # mal
  if flag: return None
```
- Separa el símbolo `#` del contenido del comentario con un espacio en blanco
```python
  # good comment
  #bad comment
```

## Nombres

- Usar `snake_case` para módulos, variables, atributos, funciones y nombre de
  métodos. NO USAR `CamelCase`.
- Usar `CamelCase` para el nombre de las clases.
- Los nombres deben referirse a lo que hace o contiene la variable, clase o
  función.
- No incluya el tipo de la variable en su nombre. Ej: use `personas` en lugar de
  `lista_personas`.

## Docstrings

- Escriba los docstrings contenidos con triple comillas dobles `"""`

- Escriba los docstrings para métodos que no sean tan simples. En los mismos
  resuma descripción de comportamiento, argumentos, valores de retorno,
  excepciones que se pueden lanzar
```python
  def some_method(name, state=None):
      """This function does something

      :param name: The name to use
      :type name: string
      :param state: Current state to be in (optional, default: None)
      :type state: bool
      :returns:  int -- the return code
      :raises: AttributeError, KeyError
      """
      ...
      return 0
```

## Imports

- Evite los import relativos utilice import absolutos
- Nunca use `*` en los imports. Siempre sea explícito sobre lo que va a importar
- Los imports deben escribirse en el siguiente orden separados por una línea:
  - Módulos build-in (que vienen con Python)
  - Módulos third-party (paquetes externos que instaló)
  - Módulos del proyecto actual
```python
  import os
  import logging

  import flask
  from flask import url_for

  from app.models.user import user
```
## Malas ideas

- Variables globales
- Usar lambdas donde no se requiere
- Usar funciones embebidas

## Fuentes

- [PEPs](https://www.python.org/dev/peps/)
- [PEP8](https://www.python.org/dev/peps/pep-0008/)
- [PEP257](https://www.python.org/dev/peps/pep-0257/)
