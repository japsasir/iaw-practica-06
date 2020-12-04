# iaw-practica-06
Práctica seis de la asignatura IAW de 2º de Asir.

> IES Celia Viñas (Almería) - Curso 2020/2021
Módulo: IAW - Implantación de Aplicaciones Web
Ciclo: CFGS Administración de Sistemas Informáticos en Red

**Introducción**
En esta práctica usaremos una pila LEMP, usando Nginx en vez de Apache. Se ha modificado el script front_end de prácticas anteriores para integrar el servidor nginx a tal efecto.

**Archivos en el repositorio**
------------
1. `lemp.sh`—Script de bash para instalar los elementos en el servidor front-end. Carpeta diferenciada. Versión nginx.
2. `default`-Archivo para Nginx que sustituye al que viene por defecto. Altera, entre otras cosas, la ruta fastcgi para que conecte por 127.0.0.1:9000
3. `back_end.sh`-Script de bash para instalar los elementos en el servidor back-end. Carpeta diferenciada.
4. `README.md`—Enlace para repositorio.

**Pasos seguidos**
------------


- Montamos nuestro servidor back end con el script correspondiente.

- En nuestro servidor front_end, sacamos los archivos 'default' y 'lemp.sh'
- Ejecutamos lemp.sh

**Archivos de configuración alterados durante el script**
------------
```bash
/etc/php/7.4/fpm/php.ini
/etc/nginx/sites-available/default
```



**Errores**
------------

- Ha ocurrido un error por instalar el módulo 'php' sin necesidad.
- Otro error ha ocurrido al intentar usar la línea
`sed -i "s#listen = /run/php/php7.4-fpm.sock#listen = 127.0.0.1:9000#" /etc/php/7.4/fpm/pool.d/www.conf`

**Referencias**
------------
- ¿Por qué el cambio a `cgi.fix_pathinfo=`? Seguridad adicional.
https://nealpoole.com/blog/2011/04/setting-up-php-fastcgi-and-nginx-dont-trust-the-tutorials-check-your-configuration/
- Guía original para la práctica.
https://josejuansanchez.org/iaw/practica-06-teoria/index.html#opci%C3%B3n-1-nginx-y-php-fpm-se-ejecutan-en-la-misma-m%C3%A1quina