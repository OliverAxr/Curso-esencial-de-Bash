# Curso-esencial-de-Bash
Curso esencial de Bash

Orientación 

pwd : Saber la ruta en disco donde te encuentras

ls : listar los archivos dentro de un directorio

ls -l : listar los archivos dentro de un directorio con lista de detalles

ls -a : lista todos los archivos dentro de un directorio incluyendo los directorios y archivos ocultos.

ls -lh : listar los archivos dentro de un directorio con lista con peso de archivos en KB, MB, o GB

ls /(Directorio) : lista el el contenido de un directorio especifico sin moverse a el

ls *.extensión : listar contenido filtrado por el tipo de extensión 

ls 03* : listar contenido filtrado nombre que inicia con 03 y tiene 0 o mas careteres al frente

ls 03*.ext: listar contenido filtrado nombre que inicia con 03 y tiene 0 o mas careteres al frente y por extensión espesificada.

ls ? :  listar contenido filtrado por numero de caracteres especifico en el nombre

cliente tree
da una vista desplegada del contenido de un directorio

find buscar archivos
find . -name "nombre" : busca archivos en el directorio donde estas

find . -name "léeme.txt"

*******************************************************

Navegación

cd : es para desplazarse entre directorios 
cd (Directorio) : Se desplaza hacia adelante 
Ejemplo : cd Documentos
cd .. : Se desplaza hacia atrás
cd ../../../ : Se desplaza hacia atrás a dependiendo de cuantos retrocesos requieras por cada ../

cd y tecla TAB : te muestra los directorios dentro del directorio actual 
cd (Ruta de directorios) : Se desplaza puntualmente a la ruta escrita
Ejemplo : cd /users/mi/user/Documentos
cd ~ : Regresas al origen de directorios del usuario

*******************************************************

Comandos Basicos

whoami: obtener el usuario del equipo en el que estas
cal: abre calendario en formato de mes actual
date: fecha y hora
uptime : tiempo de actividad del equipo
hostname: nombre del equipo
uname : versión de SO
uname -a : versión de SO mas detallada
clear: limpiar pantalla - haciendo scroll de pantalla a un espacio en limpio

*******************************************************

obtener documentación (manual) de algún comando
man (comando)
se presiona la tecla "Q", para salir de ahí

Ejemplo:
man ls


obtener ayuda del comando (puede ser uno u otro)
comando --help
comando -h

Ejemplo
ls --help
ls -h

*******************************************************

Ejercicios de lo anterior
* En la terminal, muestra el directorio en el que estas ahora
* Cambia al directorio Documentos de tu sistema
* Vuelve al mismo directorio Documentos, pero esta vez usando una ruta absoluta completa
* Sube un nivel de la jerarquía de directorios
* Lista el contenido del directorio actual, en formato simple, formato largo y finalmente incluyendo archivos ocultos
* Consulta el manual de algún comando
* Consulta la ayuda de algún comando
* Muestra tu nombre de usuario, la fecha y hora actuales y el calendario de este mes.
* Regresa al directorio donde comenzaste en el primer ejercicio
*Limpia pantalla

******************************************************

directorios por defecto


/ - raíz = C:\
/home - espacio del usuario = C:\users\miuser\
/etc - ficheros de configuración de sistema = C:\Programdata
/bin - programas base del SO =  C:\Windows\system32\
/usr - programas adicionales = C:\ProgramFiles\
/var - almacenamiento de variables = C:\users\miuser\appdata
/tmp - almacenamiento de temporales = C:\Windows\system32\temp

******************************************************

Gestionar directorio y archivos

mkdir Directorio: crea una nueva carpeta
mkdir pruebas

rmdir directorio: Elimina carpeta
rmdir pruebas

cp : puede copiar directorios o archivos, y se puede combinar con otras opciones, para copiar de un lugar a otro, copiar archivo renombrendolo (teniendo encuenta el tipo de extensión del archivo ofiginal)

cp (Directorio o Archivo) (NombreyExtensionDeDestino)
cp License Licencia.txt

Copia recursiva : Copiar una directorio con archivos dentro de otro directorio
cp -r Course Curso

Copia todo : Copia archivos de un directorio dentro de otro directorio
cp -a Course Curso


mv : mover directorios y archivos
mv (origen) (destino)
mv Archivo destino
mv License Course/

mv origen del archivo destino
mv Course/license ./

mv origen destino con otro nombre
mv readme.md léeme.md

rm : Elimina archivos

rm Archivo (eliminado permanente)

rm -r Directorio
rm -r Curso/
rm -ri Curso/ (eliminado interactivo)
rm -rf 


rm ?.extensión
rm ?.txt eliminar archivos por el numero de carraceters en su nombre y extensión espesifica

*************************************************

Crear un directorio
Elimina el directorio que acabas de crear
Copiar un archivo en el directorio actual y fuera de este
Mueve un archivo del directorio actual
cambia el nombre del archivo que acabas de mover
Lista todos los archivos de un tipo usando comodin
Elimina un directorio de manera recursiva (cuidado con lo que vas a borrar)
Elimina todos los archivos de un mismo tipo (cuidado con lo que vas a borrar)
Utiliza el comando tree
Busca un archivo concreto en el directorio actual usando find

*************************************************

Lectura de archivos

cat archivo: visualizar archivo terminal y desplazar por scroll

less archivo: visualizar archivo en visor y desplazar por bloques 

more archivo: visualizar archivo en terminal y desplazar por renglon

head archivo: visualizar archivo en terminal y muestra las primeras 10 líneas

head -n # archivo: visualizar archivo en terminal y muestra las líneas que definas colocando el numero de líneas a visualizar después del -n


tail archivo: visualizar archivo en terminal y muestra las ultimas 10 líneas

tail -n # archivo: visualizar archivo en terminal y muestra las líneas que definas colocando el numero de líneas a visualizar después del -n

tail -f archivo: visualizar archivo en terminal y muestra las ultimas 10 líneas aunque el archivo se este actualizando

grep busca algo definido dentro del archivo
grep "Objet" archivo

grep -i : busca incluyendo mayúsculas y minúsculas 

grep -r : busca lo definido en todos los archivos dentro del directorio

wc : contar elementos dentro del archivo
wc -l : líneas
wc -w: palabras
wc -c: bites contados (caracteres)

*****************************************************

Redirecciones y pipes (

Redireccionar la salida de un comando hacia otro metodo
>
>>
<
Crear archivo con la información de una salida de comando
echo "Hola" > hello.txt

sumar información de una salida de comando a algún archivo existente
echo "Alias" >> hello.txt


usar los datos de un archivo para realizar una accion
sort < hello.txt


Crear combinaciones de comandos
|

cat archihvo-txt | grep "Object" | wc -w
+++++++++++++++*****************************+++++++++++

Variable de entorno

echo $0
echo $HOME
echo $PATH

Variable local - Solo se muestra en la sesión en curso
name = Oliver

Variable global - Se muestra en todas las sesiones
abrir .bash_profile


export NOMBRE="Oliver"

*****************************************************

* Muestra todo el contenido de un archivo
* Muestra el contenido paginado de un archivo
* muestra las 15 primeras líneas de un archivo
* muestra las 15 ultimas líneas de un archivo
* busca una palabra en un archivo
* cuenta las líneas de un archivo
* redirige una salida y guardala en un archivo
* añade una nueva salida al archivo anterior
* encadena 3 comandos
* crea una variable local y muestrala
 

*****************************************************

Tipos de permisos y usuarios

Tipos de permiso

lectura = r
escritura = w
ejecución = x


Tipo de usuario
Usuario propietario = u
grupo = g
otros = o
todos = a

Ver permisos en archivos: ls -l 
ver permisos en directorios : ls -ld

-rw-r--r-- Oliver

Sintaxis Visual
[-][rw-][r--][r--]

bloque 1 [-] = tipo de archivo
bloque 2 [rw-] = permisos de usuario
bloque 3 [r--] = permisos de grupo
bloque 4 [r--] = otros usuarios


lectura = r = 4
escritura = w = 2
ejecución = x = 1

Modificar permisos

comando usuario add/rest permiso archivo

chmod u+x archivo.ext = añadir permiso
chmod u-x archivo.ext = restar permiso


chmod 777 archivo.ext = añade permisos totales
chmod 700 archivo.ext = solo permisos completos como usuario

el tiene es el resultado de la suma de los valores de cada permisos y las diferentes variaciones puede dar un numero diferente entre 0 y 7

cambiar de propietario

chown usuario archivo
chown usuario:grupo archivo

mascara de permisos (permisos que resta por defecto al crear archivos y carpetas)
umask
0022

0 - sistema octal
0 - usuario (no quita permisos)
2 - grupos (quita permiso de escritura)
2 - otros (quita permisos de escritura)

se calcula de inicio en 777 permisos máximos para directorios y se resta la mascara llegando al 755 (drwxr-xr-x)
se calcula de inicio en 666 permisos máximos para archivos y se resta la mascara llegando al 644 (rwxr--r--)

*****************************************************

* Crea un archivo y visualiza sus permisos
* Otorga permisos de ejecución solo al propietario en modo simbólico
* Cambia sus permisos a 644
* Elimina los permisos para el grupo
* Haz que solo pueda ejecutarse por el propietario
* Crea una carpeta y dale permisos para que solo el usuario pueda acceder
* Cambiale el propietario a otro usuario de tu sistema (si existe y tiene permisos)
* Consulta la mascara de permisos actual y calcula que permisos por defecto tendrán los nuevos archivos.
* Cambia la mascara crea un archivo y consulta los permisos por defecto del archivo
* Utiliza un comando como superusuario.


*****************************************************

procesos

ps - lista de procesos
ps aux  - lista detallada de procesos en ejecución 
top - lista de procesos en tiempo real
htop - lista de procesos en tiempo real con mejora visual
df -h : espacios en discos
du -sh: peso total del directorio en disco
du -sh*: detalla el peso de todos los elementos dentro del directorio


jobs : muestra procesos que se ejecutan en segundo plano

kill PID : finalizar procesos 
kill -9 PID : finalizar procesos de manera forzada



Historial de comandos

history : muestra el lista de comandos realizados en la sesión de la terminal

!!: lanza el ultimo comando ingresa

!numero: lanza el comando que se encuentra en ese numero en el historial

Alias
crear una referencia a un comando largo para la sesion
alias ll='ls -lh'

eliminar alias
unalias ll

*******************************************************

* Muestra todos los procesos del sistema
* Muestra el monitor interactivo de procesos.
* Utiliza el comando free de manera correcta (revisar)
* Lanza sleep 100 en la terminal, suspendelo, mandalo al segundo plano y traelo al primer plano (revisar)
* Lanza un proceso como sleep y terminalo usando su PID
* Consulta espacio en disco
* Consulta el historial
* Repite el ultimo comando
* Crea y prueba un alias
* Elimina el alias que acabas de crear.


*******************************************************
poner todo en un directorio

shbank

#!/bin/bash #indica con que Shell tiene que ejecutar el archivo
#Mi primer script
echo "Hola, este es mi primer script en bash"
date
echo "Tu directorio actual es: $(pwd)"
name="Oliver"
echo "Hola, $name"
a=5
b=3
let sum = a + b
echo "La suma es $sum"
let sum2 = $((a+b))
echo "La suma2 es $sum2"


añadir permisos al archivo de script
chmod +x archivo.sh


*******************************************************
lectura de datos

read_script.sh

#!/bin/bash

echo "¿Cuál es tu nombre?"
read name
echo "Hola, $name"
read -p ¿Cuál es tu edad? age
echo "Tu edad es $age"

*******************************************************
Script con parámetros (script dinamico)

#!/bin/bash
echo "El nombre del script es: 0"
echo "El primer parámetro es: $1"
echo "El segundo parámetro es: $2"
echo "Numero de parametrod: %#"
echo "El primer parametrome es :$@

se ingresa la entrada separando por espacio los parametros

*******************************************************

* Crea un script que imprima en pantalla: Hola, mundo desde bash
* Crea un script que muestre a fecha y directorio actual
* Crea un script que guarde tu nombre en una variable y lo muestre en pantalla
Crea un script que declare 2 variables numéricas, las sume, reste y multiplique, mostrando el resultado de cada operación
* Crea un script que pida tu nombre con read y muestre
* Crea un script que pida 2 números al usuario y muestre el resultado
* Crea un script con 3 argumentos que muestren el primero y tercero
* Crea un script con argumentos que muestre el numero total
crea un script que reciba 2 números como argumentos y muestre su suma, resta, multiplicación y división
* Crea un script que cree un archivo de texto y guarde tu nombre en su interior.


*******************************************************
Logica: Condicionantes

#!/bin/bash
num=15
if [ $num -ge 10 ]; then
	echo "Numero mayor o igual que 10"
elif [ $num -eq 0]; then
	echo "El numero igual a 0"
else
	echo "Condición por defecto"
fi
read -p "Elige una opción (1/2/3): " option
case $option in
	1) echo "Elegiste 1";;
	2) echo "Elegiste 2";;
	3) echo "Elegiste 3";;
	*) echo "Opción no valida";;
esac

buscar los operadores comparadores en lenguaje bash
<
>
=
=!
=<
=>


********Revisar todo lo de lógica de nuevo*********


Cron Jobs - tareas programadas

* * * * * : define el tiempo en el que se inicia la tarea, en minutos, horas, días, meses, días de la semana y cada asterisco equivale a uno de esos

59 23 31 12 6
