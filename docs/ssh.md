# SSH

La idea de esta guía es generar una clave ssh en la máquina en donde vamos a
trabajar durante la cursada para luego agregarla a el servidor Gitlab.
Con este método de seguridad vamos a evitar tener que completar usuario y clave
cada vez que realicemos una operación hacia el servidor.

## Requisitos

Para la generación de clave necesitamos ejecutar el comando `ssh-keygen`. El
mismo viene instalado en las distribuciones más comunes de linux. Para el caso
de windows cuando instalen git van a obtener la consola Git Bash.

## Generación de clave

Para generar la clave ssh deberá ejecutar el siguiente comando:

```bash
ssh-keygen -t rsa -b 2048 -C "email@example.com"
```

!!! warning
    Recuerda poner tu email en lugar de usar "email@example.com".

Se debe visualizar una respuesta similar a:

```bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/user/.ssh/id_rsa):
```

Presione la tecla Enter para guardar las llaves en el subdirectorio `.ssh/`
dentro del directorio de su usuario. Sino puede completar una ruta alternativa.

Luego de guardar la clave le pedirá que inserte in passphrase como una instancia
más de seguridad.

```bash
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Este password no es obligatorio así que puede dejarlo en blanco
pulsando nuevamente la tecla Enter.

!!! Info
    Si necesita cambiar esta passphrase en algún momento puede ejecutar el siguiente 
    comando

    ```bash
    ssh-keygen -p -f /path/to/ssh_key
    ```

Cuando el comando finaliza debería mostrarle una salida similar a la siguiente:

```bash
Your identification has been saved in /your_home/.ssh/id_rsa.
Your public key has been saved in /your_home/.ssh/id_rsa.pub.
The key fingerprint is:
a9:49:2e:2a:5e:33:3e:a9:de:4e:77:11:58:b6:90:26 mail@example.com
The key's randomart image is:
+--[ RSA 2048]----+
|     ..o         |
|   E o= .        |
|    o. o         |
|        ..       |
|      ..S        |
|     o o.        |
|   =o.+.         |
|. =++..          |
|o=++.            |
+-----------------+
```

