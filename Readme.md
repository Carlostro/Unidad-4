#  Practicas con programa Make


## Ejercicio Hola mundo.
---
En este ejercicio hemos practicado la compilación del fichero hola.c .
La compilación la hemos realizado con la función (gcc) a la cual le hemos añadido diferentes parámetros como es el caso
de(-o ) que nos permite darle el nombre que queramos al fichero de salida.

También hemos visto el argumento (-Wall -g) que nos muestra los warnings que encuentre a la hora de compilar el fichero.
Por último utilizamos la funcion make que crea un fichero ejecutable al igual que gcc o cc
escribiendo make y a continuación el nombre del archivo a compilar. "make hola"

**En la carpeta del ejercicio se ha añadido una carpeta de capturas donde se pueden ver las prácticas realizadas y los resultados.**

<br>

## Ejercicio Calculadora.
---
En este ejercicio hemos hecho una calculadora simple en un fichero (calc.c) en el que incluía la llamada a un archivo cabecera
muy comun como es el caso del <stdio.h> el cual nos permite utilizar la funcion printf, a continuacion hemos definido las funciones suma, resta, multiplicacion y division.
Estas funciones vienen formadas por:

**Tipo de dato (int) + nombre de la funcion (suma) + argumentos entre parentesis (se compone de el tipo de dato acompañado de la variable ).**

		int suma(int op1,int op2)

A continuación tenemos la última orden RETURN que nos devuelve el resultado de la funcion.

			return (op1+op2)
Quedando como resultado :


		int suma(int op1,int op2){
			return (op1+op2);
		}
Esto se repite para las diferentes funciones utilizadas en la calculadora.


	int resta(int op1,int op2){
    	return (op1-op2);
	}
	int multiplica(int op1,int op2){
    	return (op1*op2);
	}
	int divideix(int op1,int op2){
    	return (op1/op2);
	}

En el ejercicio se pide añadir una función de mayor que quedaría de la siguiente forma:

	int major(int op1,int op2){

    	if(op1>op2)
           return op1;
   		else
		   return op2;

	}

La siguiente parte del programa es la llamada a la función principal (main).
Esta parte del programa es donde se ejecutan las funciones que hemos definido anteriormente.

    int main(){
    int a=10;
    int b=5;

    printf("La suma de %d i %d és %d\n", a, b, suma(a,b));
    printf("La resta entre %d i %d és %d\n", a, b, resta(a,b));
    printf("La multiplicació de %d i %d és %d\n", a, b, multiplica(a,b));
	printf("La divisió entre %d i %d és %d\n", a, b, divideix(a,b));
	}

Si ejecutamos el programa después de compilarlo nos retornara el resultado de las operaciones que hemos declarado.


	$ ./calcula
	La suma de 10 i 5 és 15
	La resta entre 10 i 5 és 5
	La multiplicació de 10 i 5 és 50
	La divisió entre 10 i 5 és 2


También se nos pide que creemos nuestra propia librería y que la implementemos.

El resultado final son tres archivos :

+ calc.c (Donde estan implementadas las funciones que hemos programado).
+ calc.h (Este archivo es la librería creada ,definición de funciones).
+ calcula.c (codigo fuente donde hace la llamada y tenemos la función main).

**En la carpeta del ejercicio se ha añadido una carpeta de capturas donde se pueden ver las prácticas realizadas y los resultados**

<br>

## Ejercicio creación de archivo Makefile.
---
En este ejercicio hemos creado un archivo Makefile.

El formato de un Makefile consiste en un conjunto de reglas, generalmente de la siguiente forma:

	target: ficheros_necesarios

	orden

	orden

**Target** : Indica el nombre o nombres de los ficheros objeto, es decir, que se va a crear con esa regla.Normalmente se especifica un único objectivo por regla.

**Ficheros_necesarios** : És la lista de ficheros, separados por espacios que necesitamos que existan para generar el target.

**Orden** : Són las diferentes ordenes o pasos que se tienen de realizar con los ficheros_necesarios para obtener el target.
Estas línias empiezan con un tabulador, no con espacios.

Con esta información creamos el archivo Makefile donde para obtener el archivo calcula necesitamos los archivos calcula.c y calc.o.

Para poder obtener el archivo calc.o que necesita el target anterior creamos otro target para el que necesitaremos el archivo calc.c.

A continuación tenemos el ejemplo de como queda nuestro archivo.

	calcula: calcula.c calc.o

		gcc -Wall -g calcula.c calc.o -o calcula

	calc.o: calc.c calc.h

		gcc -g -Wall -c calc.c -o calc.o

El ejercicio nos proponer lanzar el archivo de diferentes formas:

-Escribiendo **make** en nuestro terminal ejecutará primero el target calcula pero si necesita algún archivo que no tiene automaticamente    ejecutará el siguiente target que crea el archivo necesario.
-Escribiendo **make calcula** ocurre lo mismo que con el comando make.
-Escribiendo **make calc.o** solo lanza el segundo target que nos crea el archivo calc.o.

El ejercicio tambien nos pide invertir los targets dentro de nuestro archivo Makefile con los siguientes resultados:

-Escribiendo **make** o **make calc.o** obtenemos el mismo resultado lanzando unicamente el target que crea el archivo calc.o.
-Escribiendo **make calcula** lanza los dos targets ya que al lanzar el target calcula busca el archivo necesario calc.o que lo obtiene lanzando el sihiente target.

**En la carpeta del ejercicio se ha añadido una carpeta de capturas donde se pueden ver las prácticas realizadas y los resultados**
