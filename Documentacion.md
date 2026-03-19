📘 Documentación – Calculadora con Árbol de Expresión
🧾 Descripción General

La aplicación AppCompleta es una calculadora desarrollada en Java con interfaz gráfica (Swing) que permite:

Validar expresiones matemáticas

Convertir expresione infijas a postfijas

Construir un árbol de expresión

Recorrer el árbol en distintos órdenes

Evaluar la expresión con valores ingresados por el usuario

🧩 Estructura del Proyecto
🔹 Clase Principal
public class AppCompleta extends JFrame

Gestiona la interfaz gráfica y coordina la lógica del programa.

🌳 Clase Nodo

Representa cada nodo del árbol de expresión.

static class Nodo {
    String valor;
    Nodo izquierda, derecha;

    Nodo(String valor) {
        this.valor = valor;
    }
}
🔸 Atributos

valor: operador o operando

izquierda: nodo hijo izquierdo

derecha: nodo hijo derecho

🌲 Clase ArbolExpresion

Encargada de construir y recorrer el árbol de expresión.

🔹 Métodos principales
✅ construirArbol
public Nodo construirArbol(String expr)

Construye el árbol a partir de la expresión infija.

✅ infijoAPostfijo
public List<String> infijoAPostfijo(String expr)

Convierte una expresión infija a postfija usando una pila.

✅ Recorridos del árbol

Inorden

izquierda → raíz → derecha

Preorden

raíz → izquierda → derecha

Postorden

izquierda → derecha → raíz
🔹 Operadores soportados

+ suma

- resta

* multiplicación

/ división

^ potencia

√ raíz cuadrada

🧮 Clase Evaluador

Evalúa la expresión en formato postfijo.

🔹 Método principal
public static double evaluar(List<String> postfija, Map<String, Double> valores)
🔸 Funcionalidad

Usa una pila (Stack)

Sustituye variables por valores ingresados

Aplica operaciones matemáticas

✅ Clase Validador

Valida que la expresión sea correcta.

🔹 Método
public static boolean esValido(String expr)
🔸 Validaciones

Solo caracteres permitidos

Paréntesis balanceados

No caracteres inválidos

🖥️ Interfaz Gráfica
Componentes

JTextField: ingreso de expresión

JTextArea: muestra resultados

JButton: ejecuta el cálculo

Layout

Norte: campo de texto

Centro: área de resultados

Sur: botón

⚙️ Flujo de Ejecución

Usuario ingresa una expresión

Se valida la expresión

Se identifican variables

Se solicitan valores al usuario

Se convierte a postfijo

Se construye el árbol

Se realizan los recorridos

Se evalúa la expresión

Se muestran resultados

📌 Ejemplo de Uso
Entrada
(a+b)*c
Valores
a = 2
b = 3
c = 4
Salida
Inorden: a + b * c
Preorden: * + a b c
Postorden: a b + c *

Resultado: 20
⚠️ Manejo de Errores

Expresión inválida → mensaje al usuario

Error en evaluación → capturado con try-catch

🛠️ Requisitos

Java JDK 8 o superior

Entorno compatible con Swing

Posibles Mejoras

Soporte para números de varios dígitos

Funciones trigonométricas

Interfaz más moderna (JavaFX)

Validación más robusta

Autor

Proyecto académico enfocado en:

Estructuras de datos (árboles)

Expresiones matemáticas

Interfaces gráficas en Java