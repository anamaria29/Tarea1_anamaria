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

Los resultados experimentales muestran un crecimiento acelerado del tiempo de ejecución conforme aumenta el tamaño del tablero.

La simulación mantiene tiempos bajos para tamaños pequeños y medianos, pero para tamaños grandes como 1024x1024 el tiempo supera los 3 segundos por ejecución.

La gráfica log-log muestra que el comportamiento observado se aproxima a una complejidad cercana a O(n²), lo cual es consistente con el hecho de que el algoritmo debe recorrer todas las celdas del tablero en cada iteración.

---

# Conclusiones

- El Juego de la Vida puede implementarse eficientemente utilizando NumPy.
- El tiempo de ejecución depende directamente de la cantidad de celdas del tablero.
- La complejidad observada experimentalmente se aproxima a O(n²).
- Las visualizaciones permiten observar claramente la evolución de los patrones.
- El uso de notebooks facilita la reproducción de experimentos y análisis de rendimiento.
