# Comparación de dos clases de Java

En este archivo de MarkDown se comparan dos clases de Java. Ambas clases utilizan la clase "Scanner" del paquete "java.util" para leer la entrada del usuario, pero difieren en la forma en que manejan la entrada y muestran los resultados
. Una utiliza las reglas del Clean Code y el otro no.

## Clase "Sin_clean_code"

```
import java.util.Scanner;

public class Ejemplo2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();
        if (x == 10) {
            System.out.println("x es igual a 10");
        } else {
            System.out.println("x no es igual a 10");
        }
    }
}

```

La clase "Ejemplo2" es un ejemplo simple de cómo utilizar la clase "Scanner" para leer un entero introducido por el usuario y comprobar si es igual a 10. Si es igual a 10, muestra "x es igual a 10", de lo contrario, muestra "x no es igual a 10". Este código es bastante sencillo y fácil de entender, pero tiene limitaciones en cuanto a su capacidad para manejar y procesar entradas más complejas.

## Clase "Con_clean_code"

```
import java.util.Scanner;

public class Ejemplo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int valor = sc.nextInt();
        boolean esIgual = VerificarIgualdad.verificarIgualdad(valor);
        VerificarIgualdad.mostrarResultado(valor, esIgual);
    }
}

public class VerificarIgualdad {
    // Verifica si el valor es igual a 10
    public static boolean verificarIgualdad(int valor) {
        return valor == 10;
    }

    // Muestra el resultado de la verificación
    public static void mostrarResultado(int valor, boolean esIgual) {
        if (esIgual) {
            System.out.println("El valor es igual a 10");
        } else {
            System.out.println("El valor no es igual a 10");
        }
    }
}

```

La clase "Ejemplo" utiliza también la clase "Scanner" para leer un entero introducido por el usuario y comprobar si es igual a 10. Pero en lugar de realizar esta comprobación directamente en el método "main", utiliza una clase llamada "VerificarIgualdad" que contiene dos métodos, uno para verificar si el valor es igual a 10 y otro para mostrar el resultado de la verificación. Estos métodos tienen nombres significativos y explícitos y no utilizan flag arguments.

Además, el código utiliza una sola palabra por concepto y ha añadido comentarios para explicar el propósito de cada función. Esto hace que el código sea más legible, comprensible y fácil de mantener que el código anterior.

En resumen, la clase "Ejemplo" es una versión mejorada de la clase "Ejemplo2" que utiliza buenas prácticas de programación para hacer el código más claro y fácil de entender.