# Proyecto I

## Descripción 

Integrantes 
Emanuel 
Angel
Morejon

La aplicación Calculadora con Árbol de Expresión es un programa desarrollado en Java que permite al usuario ingresar expresiones matemáticas en notación infija para analizarlas, procesarlas y obtener su resultado.

El sistema implementa estructuras de datos, específicamente árboles binarios de expresión, para representar de forma jerárquica cada operación matemática. A partir de la expresión ingresada, el programa realiza una conversión a notación postfija, construye el árbol correspondiente y ejecuta distintos recorridos (inorden, preorden y postorden) para mostrar la estructura de la expresión.

Además, la aplicación permite trabajar con variables (letras), solicitando al usuario los valores necesarios para evaluar correctamente la expresión matemática.

La interfaz gráfica, desarrollada con Java Swing, facilita la interacción del usuario mediante un campo de entrada, un área de resultados y un botón para ejecutar el cálculo.

*Objetivo*

- El objetivo principal del proyecto es aplicar conceptos fundamentales de:

- Estructuras de datos (árboles binarios)

- Pilas (Stacks)

- Análisis de expresiones matemáticas

- Interfaces gráficas en Java

## Estructura

- Clase Principal:

Es la clase principal del programa y se encarga de:

Crear la interfaz gráfica (ventana)

Gestionar los eventos del usuario

Coordinar el flujo de ejecución del programa

Componentes principales:

JTextField campoExpresion: entrada de la expresión

JTextArea areaResultado: muestra los resultados

JButton boton: ejecuta el cálculo

- Clase Nodo

Representa cada nodo del árbol de expresión.

Atributos:

String valor: almacena operador o operando

Nodo izquierda: referencia al hijo izquierdo

Nodo derecha: referencia al hijo derecho

- Clase ArbolExpresion

Se encarga de construir y recorrer el árbol de expresión.

Métodos principales:

construirArbol(String expr)
Construye el árbol a partir de la expresión en notación postfija.

infijoAPostfijo(String expr)
Convierte una expresión infija a postfija usando una pila.

inorden(Nodo n, StringBuilder sb)
Recorrido: izquierda → raíz → derecha

preorden(Nodo n, StringBuilder sb)
Recorrido: raíz → izquierda → derecha

postorden(Nodo n, StringBuilder sb)
Recorrido: izquierda → derecha → raíz

- Clase Evaluador

Evalúa la expresión matemática en formato postfijo.

Método principal:

evaluar(List<String> postfija, Map<String, Double> valores)

Funciones:

Sustituye variables por valores ingresados

Aplica operaciones matemáticas

Usa una pila para resolver la expresión

- Clase Validador

Se encarga de verificar si la expresión ingresada es válida.

Método:

esValido(String expr)

Validaciones:

Caracteres permitidos

Paréntesis balanceados

Formato correcto de la expresión

*Relación entre componentes*

El usuario ingresa una expresión en la interfaz

Validador verifica la expresión

ArbolExpresion convierte y construye el árbol

Evaluador calcula el resultado

AppCompleta muestra los resultados en pantalla

## Funcionamiento
- *Ingreso de la expresión*
El usuario escribe una expresión matemática en el campo de texto.
Ejemplo:
(a+b)*c
- *Validación de la expresión*
Se verifica que la expresión sea correcta mediante la clase Validador

Se valida que:

Solo contenga caracteres permitidos

Los paréntesis estén balanceados

Si la expresión no es válida, se muestra un mensaje de error.
- *Identificación de variables*
El sistema detecta las letras dentro de la expresión (variables).
- *Conversión de infijo a postfijo*
La expresión ingresada se convierte a notación postfija usando el método:
infijo → postfijo

Resultado: (a+b)*c  →  a b + c *
- *Construcción del árbol de expresión*
A partir de la expresión postfija, se construye un árbol binario donde:

Los operandos son hojas

Los operadores son nodos internos

- *Recorridos del árbol*
Se realizan tres tipos de recorridos para mostrar la estructura:

Inorden: izquierda → raíz → derecha

Preorden: raíz → izquierda → derecha

Postorden: izquierda → derecha → raíz
- *Evaluación de la expresión*
Se evalúa la expresión postfija usando una pila:

Se leen los operandos y se apilan

Cuando aparece un operador, se aplican operaciones

Se obtiene el resultado final
- *Mostrar resultados*

Finalmente, el sistema muestra:

Recorrido inorden

Recorrido preorden

Recorrido postorden

Resultado de la operación

## Ejemplo

## 📌 Ejemplo

### Expresión ingresada

(a+b)*c

### Valores de las variables

- a = 2  
- b = 3  
- c = 4  

---

### Conversión a postfijo

a b + c *

### Recorridos del árbol

- Inorden: a + b * c  
- Preorden: * + a b c  
- Postorden: a b + c *  

### ✅ Resultado final

20

## Requisitos

## 🛠️ Requisitos

- Java JDK 8 o superior  
- Entorno de desarrollo (IDE) como:
  - NetBeans  
  - IntelliJ IDEA  
  - Eclipse  
- Sistema operativo:
  - Windows, Linux o macOS  

### Requisitos de Ejecución

- Tener Java instalado y configurado correctamente  
- Compilar el archivo `.java`  
- Ejecutar la clase principal `AppCompleta`  

### Dependencias

El proyecto utiliza únicamente librerías estándar de Java:

- `javax.swing` → interfaz gráfica  
- `java.awt` → diseño de la interfaz  
- `java.util` → estructuras de datos (Stack, List, Map, Set)  

### Conocimientos Requeridos

Para comprender o modificar el proyecto se recomienda conocer:

- Programación en Java  
- Estructuras de datos (árboles y pilas)  
- Expresiones matemáticas  
- Programación orientada a objetos
