# Simulación de Procesos Financieros — ITESO

Trabajo del curso **Simulación de Procesos Financieros** de la carrera de Ingeniería
Financiera en el ITESO, Universidad Jesuita de Guadalajara.

**Alumno:** Francisco Uriel Ledezma Chávez
**Profesor:** Gabriel Alejandro Morales Ruiz
**Periodo:** Otoño 2026 · 5.º semestre

Este repositorio reúne los notebooks de clase y las tareas entregables del curso, todos
redactados con la misma estructura: portada con metadatos, índice, secciones numeradas y
una interpretación escrita después de cada resultado, de manera que cada archivo pueda
leerse de forma independiente sin necesidad de haber estado en la sesión correspondiente.
El hilo que los une va de los números pseudoaleatorios que alimentan cualquier simulación
hasta la valuación de opciones y la medición puntual de su exposición mediante las
griegas.

---

## Contenido

| Archivo | Tipo | Tema |
|---|---|---|
| [`C01-C02 - Números pseudoaleatorios y generadores congruenciales.ipynb`](C01-C02%20-%20N%C3%BAmeros%20pseudoaleatorios%20y%20generadores%20congruenciales.ipynb) | Clase | Estimación de probabilidades por simulación y condiciones de ciclo completo en generadores congruenciales lineales |
| [`C03 - Simulación del precio del activo y valuación de una call.ipynb`](C03%20-%20Simulaci%C3%B3n%20del%20precio%20del%20activo%20y%20valuaci%C3%B3n%20de%20una%20call.ipynb) | Clase | Movimiento browniano geométrico, pago descontado de una call y contraste contra Black-Scholes |
| [`C04 - Simulación de dados y ventanas móviles de rendimiento.ipynb`](C04%20-%20Simulaci%C3%B3n%20de%20dados%20y%20ventanas%20m%C3%B3viles%20de%20rendimiento.ipynb) | Clase | Probabilidad simulada sobre un espacio muestral extenso y estabilidad de media y desviación en ventanas móviles |
| [`C05 - Valuación con datos de mercado y separación train-test.ipynb`](C05%20-%20Valuaci%C3%B3n%20con%20datos%20de%20mercado%20y%20separaci%C3%B3n%20train-test.ipynb) | Clase | Estimación de parámetros con datos reales, separación temporal de la muestra y rango razonable de precios |
| [`C07 - Griegas por diferencias finitas.ipynb`](C07%20-%20Griegas%20por%20diferencias%20finitas.ipynb) | Clase | Delta, gamma, vega, theta y rho calculadas como cocientes de diferencias y validadas contra su forma cerrada |
| [`C08 - Trayectorias del precio y valuación de una opción asiática.ipynb`](C08%20-%20Trayectorias%20del%20precio%20y%20valuaci%C3%B3n%20de%20una%20opci%C3%B3n%20asi%C3%A1tica.ipynb) | Clase | Trayectorias completas del precio con envolvente al 95% y valuación comparada de una call europea contra una asiática |
| [`T01 - Caminata aleatoria.ipynb`](T01%20-%20Caminata%20aleatoria.ipynb) | Tarea | Simulación de trayectorias de capital y comportamiento de una caminata aleatoria |
| [`T02 - Análisis de sensibilidad.ipynb`](T02%20-%20An%C3%A1lisis%20de%20sensibilidad.ipynb) | Tarea | Valuación de calls y puts por Monte Carlo, verificación de paridad y sensibilidad a los cinco parámetros del modelo |

---

## Requisitos

Los notebooks se ejecutan con Python 3.12 y dependen de `numpy`, `matplotlib`, `scipy`,
`pandas` y `yfinance`. La instalación completa se resuelve con un solo comando.

```bash
pip install -r requirements.txt
```

Si se prefiere instalar sin clonar el repositorio, la línea equivalente es:

```bash
pip install numpy matplotlib scipy pandas yfinance
```

---

## Notas de ejecución

Los archivos `C04` y `C05` requieren datos externos, ya que el primero lee
`data/aapl_historical_data_2026_h1.csv` desde la ruta relativa del repositorio y el
segundo descarga precios de Yahoo Finance en tiempo de ejecución, por lo cual ambos
necesitan que esas fuentes estén disponibles antes de correrlos. El caso de `C05` merece
una advertencia adicional: al depender de una descarga en vivo, sus cifras se mueven
conforme avanza el mercado y no reproducen exactamente las que aparecen en las celdas
guardadas. El resto de los notebooks es autocontenido, y salvo `C04`, que
sortea sus dados sin semilla, todos la fijan al inicio y por ello entregan exactamente
los mismos números que aparecen en las celdas de interpretación. El caso de `C07` es
distinto por no recurrir a la simulación en ningún punto, ya que sus derivadas se
calculan sobre una malla determinista.

Los notebooks se versionan con sus salidas incluidas, ya que las interpretaciones citan
valores concretos y perderían su referencia si las celdas se limpiaran.

---

## Estructura del repositorio

```text
.
├── C01-C02 … C08/          # Notebooks de clase, numerados por sesión
├── T01 … T02/              # Tareas entregables
├── data/                   # Series de precios usadas por los notebooks
├── docs/                   # Plantilla de entregables en Word
├── requirements.txt
└── README.md
```

`docs/` guarda la plantilla que se usa cuando una entrega del curso se pide en formato
Word —portada con metadatos y la Tarea 1 de referencias bibliográficas—, no un sitio web
renderizado. Este repositorio no publica GitHub Pages.

---

## Licencia

Código y análisis bajo [licencia MIT](LICENSE). El material didáctico del curso conserva
los derechos de sus autores y se reproduce aquí únicamente como referencia del trabajo
entregado.
