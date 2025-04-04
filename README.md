# Guía de Programación en PSeInt

Este documento contiene ejemplos prácticos de programación en PSeInt, una herramienta educativa para aprender lógica de programación utilizando pseudocódigo en español.

## 1. Declarar variables en PSeInt

Las variables son espacios en memoria que nos permiten almacenar información durante la ejecución de nuestro programa. En PSeInt, debemos declarar las variables antes de usarlas, especificando su tipo de dato.

En PSeInt, las variables se declaran con la palabra clave `Definir`, seguida del nombre de la variable y su tipo de dato. Los tipos más comunes son:

- **Entero**: Para números enteros (ej. 5, -10). Se utilizan para contar elementos, índices, edades, etc.
- **Real**: Para números con decimales (ej. 3.14, 2.5). Útiles para medidas precisas, cálculos científicos, etc.
- **Caracter**: Para texto o letras (ej. "Hola", "A"). Se usan para nombres, direcciones, mensajes, etc.
- **Logico**: Para valores verdadero/falso. Útiles para condiciones y estados.

**Sintaxis básica para declarar variables:**
```
Definir <nombre_variable> Como <tipo_dato>
```

### Ejemplo práctico: Declaración y uso de variables

```
Proceso DeclararVariables
    // Declarar variables con diferentes tipos de datos
    Definir edad Como Entero
    Definir nombre Como Caracter
    Definir altura Como Real
    Definir num1, num2, resultado Como Real
    
    // Asignar valores de ejemplo
    edad <- 25
    nombre <- "Juan"
    altura <- 1.75
    num1 <- 10
    num2 <- 20
    resultado <- num1 + num2
    
    // Mostrar los valores
    Escribir "Edad: ", edad
    Escribir "Nombre: ", nombre
    Escribir "Altura: ", altura
    Escribir "Suma de num1 y num2: ", resultado
FinProceso
```

## 2. Pedir datos al usuario

Una parte fundamental de cualquier programa interactivo es la capacidad de recibir información del usuario. En PSeInt, utilizamos las instrucciones `Escribir` y `Leer` para comunicarnos con el usuario.

- `Escribir`: Muestra mensajes o valores en pantalla
- `Leer`: Captura datos ingresados por el usuario y los almacena en variables

Esta funcionalidad es esencial para crear programas dinámicos que puedan procesar diferentes entradas y producir resultados personalizados.

### Ejemplo práctico: Interacción con el usuario

```
Proceso PedirDatos
    // Declarar variable
    Definir nombre Como Caracter
    
    // Pedir dato al usuario
    Escribir "Ingresa tu nombre: "
    Leer nombre
    
    // Mostrar saludo
    Escribir "Hola, ", nombre
FinProceso
```

## 3. Condicionales en PSeInt

Los condicionales nos permiten tomar decisiones en nuestros programas, ejecutando diferentes bloques de código según se cumplan o no ciertas condiciones. PSeInt ofrece dos estructuras principales para implementar condicionales:

### 3.1 Estructura Si-Entonces-Sino

La estructura `Si-Entonces-Sino` evalúa una condición y ejecuta un bloque de código si la condición es verdadera, o un bloque alternativo si es falsa. También permite anidar múltiples condiciones para manejar casos más complejos.

**Sintaxis básica:**
```
Si <condición> Entonces
    <instrucciones si es verdadero>
Sino
    <instrucciones si es falso>
FinSi
```

### Ejemplo práctico: Evaluación de números con Si-Entonces-Sino

```
Proceso CondicionalSi
    // Declarar variable
    Definir numero Como Entero
    
    // Pedir dato al usuario
    Escribir "Ingresa un número: "
    Leer numero
    
    // Evaluar con condicional Si
    Si numero > 0 Entonces
        Escribir "El número es positivo"
    Sino
        Si numero < 0 Entonces
            Escribir "El número es negativo"
        Sino
            Escribir "El número es cero"
        FinSi
    FinSi
FinProceso
```

### 3.2 Estructura Según-Hacer

La estructura `Según-Hacer` (similar al switch-case en otros lenguajes) es útil cuando necesitamos evaluar múltiples valores posibles de una variable. Es más limpia y eficiente que usar múltiples Si-Entonces anidados cuando comparamos una misma variable contra diferentes valores.

**Sintaxis básica:**
```
Segun <variable> Hacer
    Caso <valor1>:
        <instrucciones para valor1>
    Caso <valor2>:
        <instrucciones para valor2>
    De Otro Modo:
        <instrucciones para otros casos>
FinSegun
```

### Ejemplo práctico: Calculadora simple con Según-Hacer

```
Proceso CondicionalSegun
    // Declarar variables
    Definir opcion Como Entero
    Definir num1, num2, resultado Como Real
    
    // Mostrar menú y pedir opción
    Escribir "Elige una opción: "
    Escribir "1 - Sumar"
    Escribir "2 - Restar"
    Leer opcion
    
    // Pedir números
    Escribir "Ingresa el primer número: "
    Leer num1
    Escribir "Ingresa el segundo número: "
    Leer num2
    
    // Evaluar con Según
    Segun opcion Hacer
        Caso 1:
            resultado <- num1 + num2
            Escribir "El resultado de la suma es: ", resultado
        Caso 2:
            resultado <- num1 - num2
            Escribir "El resultado de la resta es: ", resultado
        De Otro Modo:
            Escribir "Opción inválida"
    FinSegun
FinProceso
```

## 4. Operaciones matemáticas en PSeInt

PSeInt permite realizar diversas operaciones matemáticas que son fundamentales para resolver problemas computacionales. Estas operaciones incluyen suma, resta, multiplicación, división y muchas más.

### 4.1 Operadores aritméticos básicos

Los operadores aritméticos básicos en PSeInt son:

- `+` : Suma
- `-` : Resta
- `*` : Multiplicación
- `/` : División
- `^` : Potencia
- `%` o `MOD` : Módulo (resto de la división)

### Ejemplo práctico: Cálculo de área y perímetro

```
Proceso CalculosGeometricos
    // Declarar variables
    Definir lado, perimetro, area Como Real
    
    // Pedir dato al usuario
    Escribir "Ingresa la longitud del lado del cuadrado: "
    Leer lado
    
    // Realizar cálculos
    perimetro <- lado * 4
    area <- lado ^ 2
    
    // Mostrar resultados
    Escribir "El perímetro del cuadrado es: ", perimetro
    Escribir "El área del cuadrado es: ", area
FinProceso
```

### 4.2 Fórmulas y conversiones

PSeInt es muy útil para implementar fórmulas matemáticas y realizar conversiones entre diferentes unidades o sistemas de medida.

### Ejemplo práctico: Conversión de temperatura

```
Proceso ConversionTemperatura
    // Declarar variables
    Definir celsius, fahrenheit Como Real
    
    // Pedir temperatura en Celsius
    Escribir "Ingresa la temperatura en grados Celsius: "
    Leer celsius
    
    // Realizar conversión usando la fórmula F = (C × 9/5) + 32
    fahrenheit <- (celsius * 9/5) + 32
    
    // Mostrar resultado
    Escribir "La temperatura en grados Fahrenheit es: ", fahrenheit
FinProceso
```

## 5. Procesamiento de datos múltiples

A menudo necesitamos procesar varios datos para obtener un resultado. PSeInt nos permite solicitar múltiples entradas al usuario y realizar operaciones con ellas.

### Ejemplo práctico: Cálculo de promedio

```
Proceso CalcularPromedio
    // Declarar variables
    Definir nota1, nota2, nota3, promedio Como Real
    
    // Pedir calificaciones al usuario
    Escribir "Ingresa la primera calificación: "
    Leer nota1
    Escribir "Ingresa la segunda calificación: "
    Leer nota2
    Escribir "Ingresa la tercera calificación: "
    Leer nota3
    
    // Calcular promedio
    promedio <- (nota1 + nota2 + nota3) / 3
    
    // Mostrar resultado
    Escribir "El promedio de las calificaciones es: ", promedio
FinProceso
```

## 6. Aplicaciones prácticas de condicionales

Los condicionales son especialmente útiles para tomar decisiones basadas en criterios específicos. Veamos algunos ejemplos prácticos.

### Ejemplo práctico: Verificación de mayoría de edad

```
Proceso VerificarEdad
    // Declarar variable
    Definir edad Como Entero
    
    // Pedir edad al usuario
    Escribir "Ingresa tu edad: "
    Leer edad
    
    // Verificar si es mayor de edad
    Si edad >= 18 Entonces
        Escribir "Eres mayor de edad"
    Sino
        Escribir "Eres menor de edad"
    FinSi
FinProceso
```

## 7. Arreglos (Arrays) en PSeInt

Los arreglos son estructuras de datos que nos permiten almacenar múltiples valores del mismo tipo bajo un solo nombre de variable. Son muy útiles cuando necesitamos manejar colecciones de datos relacionados.

### 7.1 Arreglos unidimensionales (Vectores)

Un vector es un arreglo de una sola dimensión, como una lista de elementos. En PSeInt, podemos declarar vectores y acceder a sus elementos mediante índices. **Es importante recordar que en PSeInt los índices de los arreglos comienzan en 1, no en 0.**

**Sintaxis básica para declarar un vector:**
```
Dimension <nombre_vector>[<tamaño>]
```

### Ejemplo práctico: Uso de vectores

```
Proceso ManipularVector
    // Declarar variables
    Definir numeros Como Entero
    Definir i, suma Como Entero
    
    // Crear un vector de 5 elementos
    Dimension numeros[5]
    
    // Asignar valores al vector
    Para i <- 1 Hasta 5 Con Paso 1 Hacer
        Escribir "Ingresa el número ", i, ": "
        Leer numeros[i]
    FinPara
    
    // Calcular la suma de los elementos
    suma <- 0
    Para i <- 1 Hasta 5 Con Paso 1 Hacer
        suma <- suma + numeros[i]
    FinPara
    
    // Mostrar resultados
    Escribir "La suma de los elementos es: ", suma
    Escribir "El promedio es: ", suma/5
FinProceso
```

### 7.2 Arreglos bidimensionales (Matrices)

Una matriz es un arreglo de dos dimensiones, como una tabla con filas y columnas. En PSeInt, podemos declarar matrices y acceder a sus elementos mediante dos índices.

**Sintaxis básica para declarar una matriz:**
```
Dimension <nombre_matriz>[<filas>,<columnas>]
```

### Ejemplo práctico: Uso de matrices

```
Proceso ManipularMatriz
    // Declarar variables
    Definir matriz Como Entero
    Definir fila, columna Como Entero
    
    // Crear una matriz de 3x3
    Dimension matriz[3,3]
    
    // Llenar la matriz con valores
    Para fila <- 1 Hasta 3 Con Paso 1 Hacer
        Para columna <- 1 Hasta 3 Con Paso 1 Hacer
            Escribir "Ingresa el valor para la posición [", fila, ",", columna, "]: "
            Leer matriz[fila,columna]
        FinPara
    FinPara
    
    // Mostrar la matriz
    Escribir "La matriz ingresada es:"
    Para fila <- 1 Hasta 3 Con Paso 1 Hacer
        Para columna <- 1 Hasta 3 Con Paso 1 Hacer
            Escribir Sin Saltar matriz[fila,columna], " "
        FinPara
        Escribir ""  // Salto de línea al final de cada fila
    FinPara
FinProceso
```

## 8. Reflexión sobre el uso de pseudocódigo

El pseudocódigo es una herramienta valiosa en el aprendizaje de la programación y en el desarrollo de soluciones a problemas computacionales. Algunas de sus ventajas son:

- **Planificación**: Permite planificar la lógica de un programa antes de implementarlo en un lenguaje de programación específico.
- **Independencia del lenguaje**: Las habilidades adquiridas con pseudocódigo son transferibles a cualquier lenguaje de programación.
- **Enfoque en la lógica**: Ayuda a concentrarse en la lógica del problema sin preocuparse por la sintaxis específica de un lenguaje.
- **Comunicación**: Facilita la comunicación de algoritmos entre personas, incluso si no conocen el mismo lenguaje de programación.

Aplicaciones del pseudocódigo en la vida real:
- Diseño de algoritmos para resolver problemas cotidianos
- Planificación de procesos en empresas
- Documentación de procedimientos
- Enseñanza de conceptos de programación
- Desarrollo de prototipos rápidos de soluciones
