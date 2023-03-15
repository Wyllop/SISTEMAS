# Actividad 6.1
## Guillermo Callizaya Fernandez 
   
   1. Recibir un número entero por teclado y decir si es positivo.   
   
   
   
   ```sh
   #!/bin/bash
   echo "Ingrese cualquier numero"
   read num 
   if [ $num -ge "0" ]
   then 
   echo "El numero es positivo"
   else
   echo "El numero es negativo"
   
   ```
   
   
   2. Recibir un número entero por teclado y decir si es negativo.

   ```sh
   #!/bin/bash
   echo "Ingrese cualquier numero"
   read num 
   if [ $num -lt "0" ]
   then 
   echo "El numero es negativo"
   else
   echo "El numero no es negativo"
   
   ```
   
   3. Recibir un número entero por teclado y decir si es igual a cero.

   ```sh
   #!/bin/bash
   echo "Ingrese cualquier numero"
   read num 
   if [ $num -eq "0" ]
   then 
   echo "El numero es igual a 0"
   else
   echo "El numero es distinto a 0"
   
   ```
   
   4. Recibir un numero entero por teclado y decir si es positivo, negativo o cero.

   ```sh
   #!/bin/bash
   echo "Ingrese cualquier numero"
   read num 
   if [ $num -gt "0" ]
   then 
   echo "El numero es positivo"
   elif [ $num -lt "0" ]
   then 
   echo "El numero es negativo"
   else
   echo "El numero es 0"   
   ```
   
   5. Comprobar si el número de parámetros introducido es igual a 3, en el caso de que sea otro número 	   mostrará un mensaje de error por pantalla.

   ```sh
   #!/bin/bash
   echo "Ingrese numero"
   read num 
   if [ $num -eq "3" ]
   then 
   echo "Los numero son $num"
   else
   echo "El numero de parametros es incorrecto 0"
   
   ```
   
   6. Recibir dos números por parámetros y lo suma. En caso de que el número de parámetros sea incorrecto mostrará un mensaje de error.

   ```sh
   #!/bin/bash
  if [ $# -eq "2" ]
  then
  suma=$(($1 + $2))
  echo $suma
  else 
  echo "Numero de parametros introducidos incorrectos"
  fi
   ```
   
   7. Recibir 3 parámetros. En el caso de que reciba un número diferente mostrará un mensaje de error. Los dos primeros serán dos números y el tercero será uno de los siguientes símbolos “+” “-“ “x” “/”, dependiendo del tercer parámetro introducido realizara la correspondiente operación. El en caso de que se introduzca un símbolo diferente, presentará un mensaje indicando cuales son las opciones correctas.

```sh 
#!/bin/bash
if [ $# -eq "3" ]; then
	if [ $3 = "+" ]; then
	echo "la suma es:" $(($1 + $2))
	else
		if [ $3 = "-" ];then
		echo "la resta es:" $(($1 - $2))
		else
			if [ $3 = "x" ];then
			echo "la multiplicación es:" $(($1 * $2))
			else
				if [ $3 = "/" ];then
				echo "la división es:" $(($1 / $2))
				else
				echo "El tercer parámetro no es +, -, x o /"
				fi
			fi

		fi
	fi
else
echo "Número de parámetros introducidos incorrecto"
fi
```			
   8. Recibir la ruta de un fichero e indicar si existe
   
```sh
#!/bin/bash

if [[ -f $1 ]]
then
    echo "El fichero si existe"
else
    echo "El fichero no existe"
fi
```
   9. Recibir la ruta de un fichero e indicar si es un directorio o un fichero.
```sh
#!/bin/bash
echo "Introduce la ruta a examinar"
read n
if [ -d $n ];then
echo "La ruta pertenece a un directorio"
fi
if [ -f $n ];then
echo "La ruta pertenece a un fichero"
fi
```   
   10. Recibir la ruta de un fichero e indicar los permisos que tiene (escritura, lectura, ejecución)
```sh
#!/bin/bash
echo "Introduce una ruta"
read n
if [ -e $n ];then
	if [ -r $n ];then
	echo "El archivo tiene permisos de lectura"
	fi
	if [ -w $n ];then
	echo "El archivo tiene permisos de escritura"
	fi
	if [ -x $n ];then
	echo "El archivo tiene permisos de ejecución"
	fi
else
echo "La ruta no existe"
fi
```
  11. Imprimir por pantalla 50 veces la palabra hola.
```sh
#!/bin/bash
for ((i=0;i<=50;i++))
do
echo $i hola

done
```
  12. Leer una palabra por teclado y mostrarla por consola. Debe realizar esta operación 10 veces.
```sh
#!/bin/bash

read -p "Introduce una palabra: " palabra

for i in {1..10}
do
    echo $palabra
done
```
  13. Recibir un número por parámetro. El programa imprimirá la palabra “hola” el número de veces indicado por parámetro.
```sh
#!/bin/bash
for ((i=1;i<=$1;i++))
do
echo $i HOLA

done
```
  14. Se debe pasar un número n por parámetro. El programa imprimirá los números del 0 al n por pantalla.
```sh
#!/bin/bash
for ((i=0;i<=$1;i++))
do
echo $i
done
```   
   15. Recibir un número n por parámetro. El programa tendrá que sumar todos los números entre 1 y n. Posteriormente mostrará el resultado de la suma por 	pantalla.
```sh
#!/bin/bash
suma=0
for ((i=1;i<=$1;i++))
do

suma=`expr $suma + $i`

done
echo "Resultado:"$suma
``` 
   16. Recibir dos números por parámetro. El programa deberá hacer que el primer parámetro tome el valor del segundo parámetro y el segundo parámetro tome el valor del primero. Por ejemplo si se introduce el 2 y el 9, en un principio $1 es 1 y $2 es 9. Tras la ejecución del programa $1 valdrá 9 y $2 1.
```sh
#!/bin/bash
NUM1=$1
NUM2=$2
echo "Valor del parámetro 1: $NUM1"
echo "Valor del parámetro 2: $NUM2"
N=$NUM1
NUM1=$NUM2
NUM2=$N
echo "Cambio del parámetro 1: $NUM1"
echo "Cambio del parámetro 2: $NUM2"
```
   17. Programa que lea palabras hasta que se escriba “:q”
```sh
#!/bin/bash
echo "Escribe una palabra: "
read n
while [ $n != :q ]
do
echo "Escriba otra palabra: "
read n
done
```   
   18. Programa que lea palabras y las guarde en un fichero, hasta que se escriba “:q”
```sh
#!/bin/bash
echo "Escribe una palabra: "
read n
while [ $n != :q ]
do
echo $n >> fichero
echo "Escriba otra palabra: "
read n
done
```   
   19. Programa que lea palabras y las guarde en un fichero de forma ordenada, hasta que se escriba “:q”
```sh
#!/bin/bash
#!/bin/bash

palabra="";
archivo=fichero18.txt

if [[ -f "$archivo" ]]
then
    rm "$archivo"
fi

while [ "$palabra" != ":q" ]
do
    read -p "Escribe una palabra: " palabra
    if [[ "$palabra" != ":q" ]]
    then
        echo "$palabra" >> "$archivo"
    fi
done
```   
   20. Realiza un programa que solicite un número y compruebe si se encuentre en un archivo llamado números.txt
```sh
#!/bin/bash
archivo="numeros.txt"
read -p "Introduce un número: " num

if  grep -q "$num" "$archivo"
then
    echo "El numero $num se encuentra en el $archivo"
else
    echo "El numero $num no se encuentra en el $archivo"
fi




