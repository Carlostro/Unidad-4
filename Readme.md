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
En este ejercicio hemos hecho una calculadora simple en un fichero (calc.c) en el que incluia la llamada a un archivo cabezera
muy comun como es el caso del <stdio.h> el cual nos permite utilizar la funcion printf, a continuacion hemos definido las funciones suma, resta, multiplicacion y division.
Estas funciones vienen formadas por: 

**Tipo de dato (int) + nombre de la funcion (suma) + argumentos entre parentesis (se compone de el tipo de dato acompañado de la variable ).**

		int suma(int op1,int op2)

A continuacion tenemos la ultima orden RETURN que nos devuelve el resultado de la funcion.

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

En el ejercicio se pide añadir una funcion de mayor que quedaria de la siguiente forma:

	int major(int op1,int op2){
    
    	if(op1>op2)
           return op1;
   		else
		   return op2;
           
	}

La siguiente parte del programa es la llamada a la funcion principal (main).
Esta parte del programa es donde se ejecutan las funciones que hemos definido anteriormente.

    int main(){
    int a=10;
    int b=5;

    printf("La suma de %d i %d és %d\n", a, b, suma(a,b));
    printf("La resta entre %d i %d és %d\n", a, b, resta(a,b));
    printf("La multiplicació de %d i %d és %d\n", a, b, multiplica(a,b));
	printf("La divisió entre %d i %d és %d\n", a, b, divideix(a,b));
	}

Si ejecutamos el programa despues de compilarlo nos retornara el resultado de las operaciones que que hemos declarado.


	$ ./calcula
	La suma de 10 i 5 és 15
	La resta entre 10 i 5 és 5
	La multiplicació de 10 i 5 és 50
	La divisió entre 10 i 5 és 2


Tambien se nos pide que creemos nuestra propia libreria y que la implementemos.

El resultado final son tres archivos :

+ calc.c (Donde estan implementadas las funciones que hemos programado).
+ calc.h (Este archico es la libreria creada ,definicion de funciones).
+ calcula.c (codigo fuente donde hace la llamada y tenemos la funcion main).

**En la carpeta del ejercicio se ha añadido una carpeta de capturas donde se pueden ver las prácticas realizadas y los resultados**

<br>

## Ejercicio creación de archivo Makefile.
---
En este ejercicio hemos creado un archivo Markfile