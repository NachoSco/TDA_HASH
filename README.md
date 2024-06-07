<div align="right">
<img width="32px" src="img/algo2.svg">
</div>

# TDA HASH

## Repositorio de Nicolas Ignacio Scopel - 111305 - nscopel@fi.uba.ar

- Para compilar:

```bash
línea de compilación
```

- Para ejecutar:

```bash
línea de ejecución
```

- Para ejecutar con valgrind:
```bash
línea con valgrind
```
---
##  Funcionamiento


### Por ejemplo:


## Respuestas a las preguntas teóricas

### Definición de Diccionario:

Un diccionario es como una caja de herramientas donde guardas cosas relacionadas entre sí. Cada cosa tiene su propio nombre y puedes sacarla fácilmente si conoces su nombre. En términos más técnicos, es una estructura de datos que almacena pares de elementos: una clave (key) y un valor asociado (value). La clave es como el nombre de la cosa que quieres guardar, y el valor es la cosa misma. Con un diccionario, puedes guardar, recuperar y actualizar información de manera rápida usando estas claves. Es una forma muy útil de organizar y acceder a datos en la programación.

### Formas de Implementar un Diccionario:

1. **Tabla de Hash**:

   Una tabla de hash es como una lista grande donde guardamos cosas en posiciones específicas usando una clave.

   - **Hashing**: Imagina que tenemos una fórmula mágica (función de hash) que convierte la clave en un número que usamos como índice en la lista.
   - **Colisiones**: A veces, dos claves pueden terminar en el mismo lugar (colisión). Para manejar esto, podemos usar una lista en ese lugar o buscar el siguiente hueco libre.

   **Pros**:
   - Encontrar, agregar o borrar algo es súper rápido, normalmente toma el mismo tiempo sin importar cuántos elementos haya.
   - Perfecta si quieres velocidad.

   **Contras**:
   - Necesitas una buena fórmula mágica (función de hash).
   - Puede usar más memoria porque necesitas espacio extra para manejar colisiones.

2. **Árbol de Búsqueda Binario Balanceado (AVL)**:

   Un árbol de búsqueda binario balanceado es como un árbol donde cada nodo guarda una clave y un valor, y el árbol se autoorganiza para mantener el equilibrio.

   - **Estructura del Árbol**: Cada nodo tiene dos hijos, uno a la izquierda y otro a la derecha. Las claves a la izquierda son más pequeñas y las de la derecha más grandes.
   - **Balanceo**: El árbol se ajusta solo para no estar desbalanceado y asegurar que encontrar cosas no se vuelva lento.

   **Pros**:
   - Encontrar, agregar o borrar algo toma un tiempo razonable que crece lentamente a medida que agregas más elementos.
   - No necesitas una función de hash.

   **Contras**:
   - Más complicado de programar que una tabla de hash.
   - Puede ser un poco más lento que una tabla de hash en algunos casos.

3. **Lista Enlazada**:

   Una lista enlazada es simplemente una lista donde cada elemento apunta al siguiente.

   - **Estructura de Lista**: Cada elemento tiene una clave y un valor, y para encontrar algo tienes que empezar desde el principio y buscar hasta encontrar la clave.
   - **Inserción**: Puedes agregar elementos al principio o al final de la lista.

   **Pros**:
   - Muy fácil de programar y entender.
   - No tienes que preocuparte por colisiones ni balanceo.

   **Contras**:
   - Encontrar, agregar o borrar algo puede ser lento porque tienes que buscar a través de toda la lista.
   - No es buena para listas largas o cuando necesitas velocidad.

<div style="text-align: center;">
    <img width="800px" src="img/grafico.PNG">
</div>

## Explicación y Reseña del Gráfico:

Para analizar el rendimiento de diferentes estructuras de datos en la operación de pertenencia, se empleó Python para implementar un programa que mide el tiempo requerido para completar esta operación en tres estructuras distintas: tabla de hash, árbol de búsqueda binario balanceado y lista enlazada. Estas implementaciones se sometieron a pruebas con diferentes tamaños de datos para evaluar su desempeño en escenarios variados.

Tras recopilar los datos de rendimiento, se generó un gráfico utilizando la biblioteca de visualización de datos Matplotlib en Python. Este gráfico ofrece una representación visual clara de cómo varía el tiempo de completar la operación de pertenencia en función del tamaño de la lista para cada una de las tres estructuras de datos.

**Reseña del Gráfico:**

El gráfico exhibe el tiempo necesario para completar la operación de pertenencia en relación con el tamaño de la lista para tres estructuras de datos distintas: tabla de hash, árbol de búsqueda binario balanceado y lista enlazada. Cada línea en el gráfico corresponde a una estructura de datos, mientras que el eje x representa el tamaño de la lista y el eje y representa el tiempo en segundos.

**Conclusión:**

Al analizar el gráfico, se pueden extraer diversas conclusiones:

1. **Tabla de hash:** Presenta un tiempo de búsqueda constante \(O(1)\), independientemente del tamaño de la lista. Esto sugiere que la búsqueda en una tabla de hash es altamente eficiente y apenas se ve afectada por el tamaño de los datos.
   
   **Dificultades:**
   - **Colisiones:** Aunque es muy eficiente, puede enfrentar problemas de colisiones, que requieren técnicas adicionales como encadenamiento o direccionamiento abierto para manejarlas.
   - **Espacio:** Puede requerir una cantidad significativa de memoria si la tabla no está bien dimensionada.

2. **Árbol de búsqueda binario balanceado (ABB):** Muestra un tiempo de búsqueda que aumenta de forma logarítmica \(O(\log n)\) con el tamaño de la lista. Aunque es más lento que la tabla de hash para listas pequeñas, su tiempo de búsqueda se mantiene razonable incluso para listas más grandes.

   **Dificultades:**
   - **Complejidad de implementación:** La implementación y mantenimiento de un árbol de búsqueda binario balanceado (como un AVL o un árbol rojo-negro) es más compleja, debido a la necesidad de reequilibrar el árbol tras las inserciones y eliminaciones.
   - **Rebalanceo:** Operaciones como inserción y eliminación pueden requerir reestructuración del árbol, lo que añade complejidad y tiempo de procesamiento.

3. **Lista enlazada:** Exhibe un tiempo de búsqueda que crece linealmente \(O(n)\) con el tamaño de la lista. Este comportamiento indica que la búsqueda en una lista enlazada se vuelve considerablemente más lenta a medida que aumenta el tamaño de los datos.

   **Dificultades:**
   - **Ineficiencia:** La búsqueda en una lista enlazada es ineficiente para grandes volúmenes de datos.
   - **Acceso secuencial:** No permite acceso directo a elementos, lo que puede hacerla lenta para operaciones frecuentes de búsqueda o acceso aleatorio.

En resumen, el gráfico resalta cómo diferentes estructuras de datos pueden influir en el rendimiento de las operaciones de búsqueda según el tamaño de los datos. La elección de la estructura de datos adecuada puede tener un impacto significativo en el rendimiento de una aplicación, especialmente cuando se manejan grandes volúmenes de datos.

### Qué es una función de hash y qué características debe tener

Una función de hash es como una especie de receta secreta en la cocina. Toma algo, como una palabra o un número, y lo transforma en un código único. Es como si mezclaras ingredientes para hacer una receta especial: cada combinación de ingredientes produce un plato único.

Para ser efectiva, una función de hash debe tener algunas características importantes:

1. **Determinística**: Esto significa que siempre que le des la misma entrada, obtendrás la misma salida. Por ejemplo, si le das la palabra "perro" a la función de hash, siempre debería darte el mismo código único.

2. **Eficiente**: La función de hash debe ser rápida de calcular. No quieres esperar mucho tiempo para obtener el código único de algo.

3. **Distribución uniforme**: Esto significa que la función de hash debería producir códigos únicos que se distribuyan de manera uniforme en el espacio de salida. No quieres que muchos elementos diferentes terminen con el mismo código único.

4. **Resistencia a colisiones**: Una colisión ocurre cuando dos entradas diferentes producen el mismo código único. Si bien es difícil evitar por completo las colisiones, una buena función de hash debería minimizar la probabilidad de que ocurran. Esto es importante para evitar confusiones y mantener la integridad de los datos.

Una tabla de hash es como una caja de almacenamiento gigante donde puedes guardar cosas usando una clave para encontrarlas rápidamente. Funciona como un mapa donde asignas una clave a un valor específico y luego puedes buscar ese valor rápidamente usando esa clave. Las tablas de hash son muy eficientes para recuperar y almacenar datos, especialmente cuando tienes una gran cantidad de información para manejar.

## Qué es una tabla de Hash y los diferentes métodos de resolución de colisiones vistos ( probing lineal, probling cuadratico y hash doble)

Una tabla de hash es como una caja de almacenamiento gigante donde puedes guardar cosas usando una clave para encontrarlas rápidamente. Funciona como un mapa donde asignas una clave a un valor específico y luego puedes buscar ese valor rápidamente usando esa clave. Las tablas de hash son muy eficientes para recuperar y almacenar datos, especialmente cuando tienes una gran cantidad de información para manejar.

1. **Probing Lineal**:
   - Cuando ocurre una colisión, este método busca el siguiente índice disponible en la tabla de hash, uno por uno, de manera lineal.
   - Por ejemplo, si la clave "A" colisiona con la clave "B" en el índice 5, el método de probing lineal buscará el siguiente índice disponible hasta encontrar un lugar libre donde colocar la clave "B".

2. **Probing Cuadrático**:
   - Similar al probing lineal, pero en lugar de buscar de forma lineal, este método utiliza una secuencia de pasos cuadráticos para buscar el siguiente índice disponible.
   - Por ejemplo, si la clave "A" colisiona con la clave "B" en el índice 5, el método de probing cuadrático buscará en los índices 5, 9, 14, 20, etc., hasta encontrar un lugar libre para la clave "B".

3. **Hash Doble**:
   - En este método, cuando ocurre una colisión, se calcula un segundo valor hash a partir de la clave y se utiliza para calcular un segundo índice en la tabla de hash.
   - Este segundo índice se utiliza como un incremento adicional al índice original, permitiendo que la búsqueda se realice de manera más diversa que en los métodos de probing lineal y cuadrático.
   - Por ejemplo, si la clave "A" colisiona con la clave "B" en el índice 5, el método de hash doble calculará un segundo índice usando una segunda función hash y luego buscará en los índices 5, 8, 13, 20, etc., hasta encontrar un lugar libre para la clave "B".

<div style="text-align: center;">
  <img width="500px" src="img/Memoria_HASH.PNG">
</div>

