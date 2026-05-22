# Tarea 1: Juego de la Vida de Conway:

Simulación del Juego de la Vida utilizando Python y NumPy, incluyendo visualización animada, patrones clásicos y análisis de rendimiento computacional.

---

# Descripción de la tarea:

Este proyecto implementa el Juego de la Vida de Conway, un autómata celular donde cada celda evoluciona según unas simples reglas que se basan en los vecinos.

La simulación incluye:

- Evolución del tablero
- Patrones clásicos
- Animaciones
- Benchmark de rendimiento
- Comparación con complejidades teóricas
- Visualización log-log

--- 

# Requerimientos para correr el código:

Instalar las dependencias mediante: 

pip install -r requirements.txt

# Estructura del notebook:

El notebook se divide en:

- Imports
- Clase Juego de la Vida
- Patrones
- Visualizaciones
- Benchmark

Cada sección tiene subsecciones, tales como la especificación de tamaños y pruebas.

---

# Patrones implementados:

Se implementaron varios patrones clásicos, como:

- Glider
- Blinker
- Toad

Ejemplo:

```
initial[10:13, 10:13] = glider()
initial[20:21, 20:23] = blinker()
```

# Visualizaciones:

La simulación utiliza matplotlib.animation.FuncAnimation para generar animaciones del tablero. Por ejemplo:

'''
ani = animation.FuncAnimation(
    fig,
    update,
    frames=100,
    interval=100,
    blit=True
)
'''

Además, se generaron gráficas de rendimiento y comparaciones de complejidad temporal utilizando escalas normales y log-log.

---

# Capturas de las Visualizaciones:

## Tablero

<img width="416" height="435" alt="image" src="https://github.com/user-attachments/assets/962a6b24-2ea1-4123-bf3c-c7f1e4e4ba0c" />


## Rendimiento

<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/4e28e7e3-aa88-44e8-b9a1-1dd5da4bc37a" />

# Comparación con Complejidad Teórica

<img width="846" height="548" alt="image" src="https://github.com/user-attachments/assets/32b15792-99f0-4f6e-84cc-feb590d92e9b" />


## Visualización Log-Log

<img width="702" height="476" alt="image" src="https://github.com/user-attachments/assets/e11b14e7-4e55-44c3-a77d-ac6cf0d561cc" />

## Animación:

<img width="640" height="480" alt="output" src="https://github.com/user-attachments/assets/f10844a2-02a5-49fd-9b61-6318a21d035c" />

---

# Benchmark de Rendimiento:

Se realizaron pruebas utilizando distintos tamaños de tablero: 32, 64, 128, 256, 512, 1024. 

Los tiempos obtenidos fueron:

| Tamaño    | Tiempo (s) |
| --------- | ---------- |
| 32x32     | 0.009083   |
| 64x64     | 0.015446   |
| 128x128   | 0.055732   |
| 256x256   | 0.239858   |
| 512x512   | 0.911978   |
| 1024x1024 | 3.752434   |

Los resultados muestran que el tiempo de ejecución aumenta conforme crece el tamaño del tablero, debido a que se deben evaluar más celdas en cada iteración.

# Comparación con Curvas Teóricas:

Los resultados experimentales fueron comparados con curvas teóricas de complejidad:

- O(n)
- O(n log n)
- O(n²)

Esto mediante el uso de gráficas lineales y log-log. La gráfica log-log permite observar de forma más clara el comportamiento asintótico del algoritmo y compararlo con las curvas teóricas.

--- 

# Reproducción:

Para reproducir los experimentos se debe:

1. Instalar dependencias. 
2. Ejecutar todas las celdas del notebook
3. Ejecutar la sección de benchmark
4. Generar las gráficas
5. Ejecutar las animaciones

---

# Resultados

Los experimentos realizados permiten observar cómo cambia el tiempo de ejecución del Juego de la Vida conforme aumenta el tamaño del tablero. Para el benchmark se utilizaron tableros desde 32×32 hasta 1024×1024. Midiendo el tiempo requerido para ejecutar la simulación. Los resultados se pueden observar en la Tabla 1. A partir de estos datos se puede observar que el tiempo de ejecución aumenta conforme crece el número de celdas del tablero. Esto ocurre porque el algoritmo debe recorrer cada celda y evaluar sus vecinos, en cada iteración.

Las visualizaciones de patrones como el Glider y el Blinker, mostradas en el Gráfico 1, permiten verificar que las reglas del autómata celular fueron implementadas correctamente. Ya que, los patrones evolucionan de la forma esperada. En el caso del Glider, se observa un desplazamiento diagonal continuo a través del tablero, mientras que el Blinker alterna periódicamente entre estados horizontales y verticales. Esto confirma que las reglas de nacimiento, supervivencia y muerte de las celdas funcionan adecuadamente en cada iteración de la simulación.

En la Gráfica 3, correspondiente a la comparación con curvas teóricas, se observa que la curva experimental tiene un comportamiento muy similar a la complejidad O(n2). Esto es consistente con la naturaleza del problema, ya que al aumentar el tamaño del tablero, también aumenta la cantidad de celdas que deben de ser evaluadas en cada iteración. Puesto que, el algoritmo revisa el estado y los vecinos de cada celda, el tiempo de ejecución crece de manera proporcional al número total de celdas. Esto último, explica la tendencia observada en los resultados.

La Gráfica 4 en escala log-log, permite analizar con mayor claridad el crecimiento asintótico del algoritmo. En esta visualización, la pendiente de la curva experimental sigue una tendencia cercana a la curva cuadrática. Esto confirma que el tiempo de ejecución aumenta conforma crece el tablero. Este comportamiento evidencia que el costo computacional del algoritmo incrementa para los tableros de mayor tamaño.

---

# Conclusiones

En este proyecto se logró implementar correctamente el Juego de la Vida de Conway utilizando Python y NumPy. Permitiendo simular la evolución de distintos patrones clásicos dentro de un autómata celular. Las visualizaciones y animaciones generadas facilitaron la comprensión del comportamiento dinámico del sistema, además de permitir verificar que las reglas de evolución fueron aplicadas correctamente en cada iteración.  

Los experimentos de rendimiento mostraron que el tiempo de ejecución aumenta conforme crece el tamaño del tablero, debido a que el algoritmo debe de recorrer y evaluar cada celda, para calcular el siguiente estado. A partir de las gráficas obtenidas, especialmente la gráfica log-log, se observó que el comportamiento experimental presenta una tendencia cercana a la complejidad O(n2). Este resultado es consistente con el crecimiento cuadrático del número de celdas en la matriz.

Asimismo, el uso de NumPy permitió mejorar significativamente la eficiencia de la simulación. En comparación con una implementación completamente manual, basada en listas y ciclos tradicionales. Sin embargo, también se evidenció que para los tableros más grandes, el costo computacional y el consumo de memoria aumentan considerablemente. Esto limita el rendimiento de la simulación y demuestra la importancia de aplicar técnicas de optimización y herramientas especializadas para simulaciones de mayor escala.
