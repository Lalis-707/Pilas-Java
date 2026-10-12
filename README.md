# Pilas Estáticas y Dinámicas en Java

## 1. Descripción del proyecto
Este proyecto consiste en implementar y probar dos tipos de pilas en Java: una pila estática, utilizando un arreglo, y una pila dinámica, mediante nodos enlazados. Ambas estructuras funcionan bajo el principio **LIFO (*Last In, First Out*)**, que significa que el último elemento en entrar es el primero en salir. El objetivo es comprender sus operaciones principales y reconocer las diferencias en su almacenamiento y manejo de memoria.

## 2. Archivos del proyecto
El proyecto está organizado en los siguientes archivos Java:

- `PilaSimple.java`: contiene la implementación de la pila estática.
- `MainPSimple.java`: permite ejecutar las pruebas de la pila estática.
- `PilaDinamica.java`: contiene la implementación de la pila dinámica.
- `MainPDinamica.java`: permite ejecutar las pruebas de la pila dinámica.
- `Nodo.java`: define los nodos utilizados por la pila dinámica.

Los archivos pertenecen al paquete:

```
Estructuras_Lineales.Unidad03y04.Pila
```

## 3. Operaciones implementadas
Las pilas cuentan con métodos que permiten insertar, eliminar, consultar y mostrar sus elementos.

| Método | Descripción |
|---|---|
| `push(int x)` | Inserta un elemento en la cima de la pila. |
| `pop()` | Elimina el elemento de la cima si la pila no está vacía. |
| `mostrar()` | Muestra los elementos almacenados, comenzando por la cima. |
| `peek()` | Consulta el elemento de la cima sin eliminarlo. |
| `isEmpty()` | Comprueba si la pila está vacía. |
| `isFull()` | Comprueba si la pila está llena. Solo se utiliza en la pila estática. |

## 4. Diferencias entre las pilas estática y dinámica
### Pila estática
La pila estática almacena sus elementos en un arreglo de tamaño fijo que, en esta práctica, tiene capacidad para cinco números enteros. La variable `tope` indica la posición del último elemento insertado y comienza en `-1`, lo que significa que la pila está vacía.

Al insertar elementos, el valor de `tope` aumenta y, al eliminarlos, disminuye. El método `isFull()` permite identificar cuándo se alcanza la capacidad máxima y evitar nuevas inserciones.

### Pila dinámica
La pila dinámica utiliza nodos enlazados para almacenar los elementos. Cada nodo contiene un dato y una referencia al siguiente nodo, mientras que la variable `cima` apunta al elemento superior.

Al insertar un elemento, se crea un nuevo nodo que pasa a ser la cima. Al eliminarlo, la cima se actualiza para apuntar al siguiente nodo. Esta implementación no tiene una capacidad máxima fija definida en el código y puede crecer según la memoria disponible.

### Comparación general
La principal diferencia es que la pila estática utiliza un arreglo con capacidad definida, mientras que la dinámica crea nodos conforme se agregan elementos. Ambas permiten realizar las operaciones principales de una pila, pero manejan el almacenamiento y la memoria de manera diferente.

## 5. Instrucciones de compilación y ejecución
El proyecto puede ejecutarse desde un entorno de desarrollo integrado (IDE), como IntelliJ IDEA, Eclipse o NetBeans, o mediante la terminal utilizando el JDK de Java.

### Desde un IDE
1. Abre el proyecto en tu entorno de desarrollo.
2. Localiza el paquete `Estructuras_Lineales.Unidad03y04.Pila`.
3. Ejecuta `MainPSimple.java` para probar la pila estática.
4. Ejecuta `MainPDinamica.java` para probar la pila dinámica.
5. Revisa la consola para observar los resultados de las operaciones.

### Desde la terminal
Si los archivos están dentro de la carpeta `src`, abre una terminal en esa ubicación.

**1. Compilar los archivos Java:**
```
javac Estructuras_Lineales/Unidad03y04/Pila/*.java
```

**2. Ejecutar la pila estática:**

```
java Estructuras_Lineales.Unidad03y04.Pila.MainPSimple
```

**3. Ejecutar la pila dinámica:**

```
java Estructuras_Lineales.Unidad03y04.Pila.MainPDinamica
```

Es necesario tener instalado el JDK de Java y ejecutar los comandos desde la ubicación correcta del proyecto.

## 6. Resultados de consola
A continuación, se presentan algunas de las pruebas realizadas para comprobar el funcionamiento de ambas implementaciones.

### Prueba 1. Pila estática llena
Se insertaron cinco elementos y se intentó agregar un sexto para comprobar el control de capacidad.

```
C:\Users\David\OneDrive\Escritorio\EstructuraDeDatos\out\production\EstructuraDeDatos Estructuras_Lineales.Unidad03y04.Pila.MainPSimple
Metiste: 10
Metiste: 20
Metiste: 30
Metiste: 40
Metiste: 50
¿Está llena? true

Pila actual: 50 40 30 20 10 
¡Pila llena!

Pila actual: 50 40 30 20 10 

Process finished with exit code 0
```

**Resultado:** La pila detectó que estaba llena y rechazó la inserción del elemento `60`, conservando los cinco elementos originales.

### Prueba 2. Pila estática vacía
Se intentó retirar y consultar un elemento sin haber insertado datos.

```
"C:\Program Files\Java\jdk-26.0.2\bin\java.exe" "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA 2026.2.2\lib\idea_rt.jar=55783" -Dfile.encoding=UTF-8 -Dsun.stdout.encoding=UTF-8 -Dsun.stderr.encoding=UTF-8 -classpath C:\Users\David\OneDrive\Escritorio\EstructuraDeDatos\out\production\EstructuraDeDatos Estructuras_Lineales.Unidad03y04.Pila.MainPSimple
¿Está vacía? true
¡Pila vacía!
La pila está vacía.
Elemento en la cima: -1
¿Está vacía? true

Process finished with exit code 0
```

**Resultado:** La pila detectó que estaba vacía. La operación `pop()` no retiró ningún elemento y `peek()` devolvió `-1`, valor utilizado por esta implementación para indicar que no hay un elemento disponible en la cima.

### Prueba 3. Consulta y eliminación en la pila dinámica
Se insertaron tres elementos, se consultó la cima y posteriormente se retiró el elemento superior.

```
"C:\Program Files\Java\jdk-26.0.2\bin\java.exe" "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA 2026.2.2\lib\idea_rt.jar=55818" -Dfile.encoding=UTF-8 -Dsun.stdout.encoding=UTF-8 -Dsun.stderr.encoding=UTF-8 -classpath C:\Users\David\OneDrive\Escritorio\EstructuraDeDatos\out\production\EstructuraDeDatos Estructuras_Lineales.Unidad03y04.Pila.MainPDinamica
Elemento en la cima: 30

PILA ACTUAL:
30 20 10 
Sacaste de la pila: 30

PILA ACTUAL:
20 10 

Process finished with exit code 0
```
**Resultado:** La operación `peek()` permitió consultar el valor `30` sin eliminarlo. Después, `pop()` retiró ese nodo y los valores `20` y `10` permanecieron en la pila.

---
Los resultados corresponden a las pruebas realizadas con los programas principales. El análisis teórico, la representación gráfica del principio LIFO, los fragmentos de código comentados y las conclusiones personales se desarrollan en el reporte PDF de la práctica.
