# Taller1-Scripting-Nicole-Sofia-Jacobo
# Taller-1-Scripting

## 1. Escoja 7 enunciados: 

➨ 2 sobre uso de funciones

➨ 1 sobre arreglos o matrices

➨ 1 sobre cadenas

➨ 1 sobre condiciones o ciclos

➨ 2 preguntas de teoría

## Funciones (2)
• 11. Cree un menú infinito con 3 opciones para realizar operaciones sencillas. 

• 18. Realice una función, que lea un número de máximo 8 cifras y luego sume cada dígito hasta obtener un valor de un solo dígito.

### Solución 
```c#
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Ingresa un número de hasta 8 cifras:");
            decimal numero = decimal.Parse(Console.ReadLine()); 

            int suma = SumarDigitos(numero); 
            Console.WriteLine("El resultado es: " + suma); 
        }

        static int SumarDigitos(decimal numero)
        {
            int suma = 0;

            while (numero > 0)
            {
                suma += (int)(numero % 10); 
                numero /= 10; 
            }

            while (suma >= 10)
            {
                int tempSuma = 0;
                while (suma > 0)
                {
                    tempSuma += suma % 10; 
                    suma /= 10; 
                }
                suma = tempSuma; 
            }

            return suma; 
        }
    }
}
```

## Arreglos o matrices (1)
• 10. Lea una matriz 3D, luego cree 3 arreglos a partir de la matriz leída

### Solución 
```c#
internal class Program
    {
        static void Main(string[] args)
        {
           int columnas = 0;

 
       Console.WriteLine("Bienvenido al creador de matrices 3xn, cuantas columnas le quieres dar a la matriz?");
       columnas = int.Parse(Console.ReadLine());
       int[,] matriz = new int[3, columnas];
       Console.WriteLine("LLenemos esa matriz " + 3 + "x"+columnas);
       for (int i = 0; i < matriz.GetLength(0); i++) 
       {
           for (int j = 0; j < matriz.GetLength(1); j++)
           {
               Console.WriteLine("Ingrese el numero para la fila " + (i+1) + " y la columna " + (j+1));
               int numero = int.Parse(Console.ReadLine());
               matriz[i, j] = numero;
           }
       }
       Console.WriteLine("Ahora vamos a mostrar 3 arreglos con los numeros que llenaste, el arreglo serán las filas de esta matriz:");
       for(int i = 0;i < matriz.GetLength(0); i++)
       {
           Console.WriteLine();
           Console.WriteLine("Fila numero " + (i+1));
           for(int j = 0;j < matriz.GetLength(1); j++)
           {
               Console.Write(matriz[i, j] + " | ");                  
           }
       }
   }
}     
```


## Cadenas (1)
• 7. Lea una cadena de números enteros positivos y luego cree un array con los números de la cadena, se debe validar que la cadena obtenga números.
```c#
namespace Application
{
    class Program
    {
        static int tamanocadena = 0;
        static bool positivo = true;
        static void Main(string[] args)
        {
            
            Console.WriteLine("Por favor ingrese el tamaño que quiere para su cadena de números");
            int respuesta = int.Parse(Console.ReadLine());
            tamanocadena = respuesta;
            int[] cadena = new int[respuesta];
            Console.WriteLine("Creaste una cadena de " + tamanocadena + " numeros ahora llenemosla");
            for (int i = 0; i < cadena.Length; i++)
            {
                positivo=true;
                Console.WriteLine("Ingrese el numero " + (i+1) + " De la cadena: ");
                while (positivo){
                int numero = int.Parse(Console.ReadLine());
                if (numero <=0){
                    Console.WriteLine("por favor ingresa un número entero positivo");

                }
                else{
                    cadena[i] = numero;
                    positivo=false;
                }
                }
              
                
            }
            Console.WriteLine("A continuación la cadena que ingresaste");
            for (int i = 0; i < cadena.Length; i++)
            {
                Console.Write(cadena[i] + " | ");
            }
        }
    
    }
}
```
    
## Teoría (2)
• 12. Realice 5 condicionales usando los diferentes operadores.

### Solución 

#### Operador == (igualdad)
Compara si dos valores son exactamente iguales.

```c#
    internal class Program
    {
        static void Main(string[] args)
        {
            //Operador ==
            Console.Write("Ingresa tu salario: ");
            decimal salario = Convert.ToDecimal(Console.ReadLine());

            decimal salarioMinimo = 1423500;

            if (salario == salarioMinimo)
            {
                Console.WriteLine("Usted gana un salario mínimo legal vigente");
            }
            else
            {
                Console.WriteLine("Usted gana un valor diferente al salario mínimo legal vigente");
            }
        }
    }
}
```
#### Operador && (y lógico)
Evalúa si ambas condiciones son verdaderas para ejecutar un bloque de código.

```c#
    internal class Program
    {
        static void Main(string[] args)
        {
            //Operador &&
            Console.Write("Ingresa la hora (24h): ");
            int hora = Convert.ToInt32(Console.ReadLine());

            Console.Write("Ingresa el día de la semana: ");
            string dia = Console.ReadLine();

            if (hora >= 10 && hora <= 14 && dia == "Viernes")
            {
                Console.WriteLine("Debes estar en clase de Scripting");
            }
            else
            {
                Console.WriteLine("No estás en clase de Scripting");
            }
        }
    }
}
```
#### Operador >= o < (Mayor o igual que - Menor)
Verifica si un valor es mayor o igual a otro o compara si un valor es estrictamente menor que otro.

```c#
internal class Program
    {
        static void Main(string[] args)
        {
            //Operador >= o <
            int semestre = 0;
 
            Console.WriteLine("¿Cuál semestre estas cursando actualmente? (1-8)");
            semestre = int.Parse(Console.ReadLine());
 
            if (semestre >= 1 && semestre < 4)
            {
                Console.WriteLine("Estás cursando los primeros semestres de tu carrera, apenas estas iniciando");
            }
            if (semestre >= 4 && semestre < 7)
            {
                Console.WriteLine("Estás en la mitad de la carrera, ya has avanzado un poco");
            }
            if (semestre >= 7)
            {
                Console.WriteLine("Pronto terminarás la carrera, no te rindas");
            }
        }
    }
}
```
#### Operador != (Diferente de)
Compara si un valor es diferente de otro.

```c#
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Ingresa las siglas de tu carrera:");
            string palabra = Console.ReadLine();

            if (palabra != "ided")
            {
                Console.WriteLine("La palabra ingresada no es 'ided'.");
            }
            else
            {
                Console.WriteLine("La palabra ingresada es 'ided'.");
            }
        }
    }
}
```


#### Operador || (OR lógico)
Evalúa si al menos una de dos condiciones es verdadera.
```c#
       internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Ingresa un número:");
            int numero = int.Parse(Console.ReadLine());

            // Verificar si el número es negativo o igual a cero
            if (numero < 0 || numero == 0)
            {
                Console.WriteLine("El número es negativo o igual a cero.");
            }
            else
            {
                Console.WriteLine("El número es positivo.");
            }
        }
    }
}

```
• 7. Escriba 10 palabras reservadas

### Solución 

1- int: Define variables de tipo entero.

2- if: Establece una condición.

3- else: Define qué hacer si la condición no se cumple.

4- for: Crea un bucle controlado por un contador.

5- while: Crea un bucle basado en una condición.

6- return: Devuelve un valor desde una función.

7- float: Define variables de tipo decimal o punto flotante.

8- public: Define acceso libre para clases, métodos o variables.

9- private: Limita el acceso a elementos dentro de una clase.

10- static: Declara elementos que pertenecen a la clase, no a sus instancias.

#### ¿Por qué son palabras reservadas?

✦ Estas palabras son llamadas así porque tienen funciones específicas que el lenguaje interpreta para estructurar y ejecutar el código. No pueden usarse como nombres de variables u otros elementos, ya que el compilador las reconoce como comandos específicos asignadas a su propósito definido en el lenguaje.

## Firmas 

1- public static int CalcularSuma(int x, int y)

Invocación: int resultado = CalcularSuma(5, 10);

2- private float CalcularPromedio(float[] numeros)

Invocación: float promedio = CalcularPromedio(new float[] { 3.5f, 4.8f, 6.2f });

3- protected static void ImprimirMensaje(string mensaje)

Invocación: ImprimirMensaje("Hola, mundo!");

4- public static long CalcularFactorial(int n)

Invocación: long factorial = CalcularFactorial(10);

5- public double CalcularAreaCirculo(double radio)

Invocación: double area = CalcularAreaCirculo(3.5);

6- static string GenerarSaludo(string nombre)

Invocación: string saludo = GenerarSaludo("Juan");

7- public static int[] OrdenarArray(int[] array)

Invocación: int[] arrayOrdenado = OrdenarArray(new int[] { 5, 2, 8, 1 });

8- private static bool VerificarPrimo(int numero)

Invocación: bool esPrimo = VerificarPrimo(17);

9- public static void MostrarTablaMultiplicar(int numero)

Invocación: MostrarTablaMultiplicar(7);

10- protected static float CalcularInteres(float capital, float tasa, int tiempo)

Invocación: float interes = CalcularInteres(1000f, 0.05f, 3);

11- public static string FormatearNombre(string nombre, string apellido)

Invocación: string nombreCompleto = FormatearNombre("María", "García");

12- static int[] FiltrarNumerosPares(int[] numeros)

Invocación: int[] pares = FiltrarNumerosPares(new int[] { 1, 2, 3, 4, 5 });

13- private static void ImprimirPiramide(int niveles)

Invocación: ImprimirPiramide(5);

14- public static double CalcularPotencia(double base, int exponente)

Invocación: double resultado = CalcularPotencia(2.5, 3);

15- public static void CopiarArchivo(string origen, string destino)

Invocación: CopiarArchivo("archivo.txt", "copia.txt");

16- protected static bool ValidarEmail(string email)

Invocación: bool esValido = ValidarEmail("ided@upb.com");

17- public static int[] OrdenarDescendente(int[] array)

Invocación: int[] descendente = OrdenarDescendente(new int[] { 10, 5, 8, 3 });

18- static void ImprimirInverso(string texto)

Invocación: ImprimirInverso("Hola");

19- public static float ConvertirFahrenheitACelsius(float fahrenheit)

Invocación: float celsius = ConvertirFahrenheitACelsius(98.6f);

20- public static string ReemplazarEspacios(string texto)

Invocación: string resultado = ReemplazarEspacios("Hola Mundo");

