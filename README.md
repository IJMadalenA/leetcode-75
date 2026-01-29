# LeetCode 75 - Retos de Programación y Benchmarking

Este repositorio contiene soluciones a los retos de LeetCode 75, junto con una infraestructura para comparar el rendimiento de diferentes aproximaciones.

## Estructura del Proyecto

- `benchmark_utils.py`: Módulo de utilidad para medir tiempo de ejecución y consumo de memoria.
- `array-string/`: Carpeta con retos relacionados con arrays y strings.
  - `1768. Merge Strings Alternately.ipynb`: Ejemplo de implementación y benchmarking.

## Cómo usar la plantilla de Benchmarking

Para comparar diferentes soluciones en un Notebook:

1. Define tus soluciones en clases separadas (ej. `MySolution`, `BestRuntimeSolution`).
2. Importa las utilidades de benchmarking:
   ```python
   import sys, os
   sys.path.append(os.path.abspath(os.path.join(os.getcwd(), "..")))
   from benchmark_utils import run_benchmark, print_results
   ```
3. Configura las funciones y los casos de prueba:
   ```python
   functions = [MySolution.mergeAlternately, OtherSolution.mergeAlternately]
   test_cases = [{"word1": "abc", "word2": "pqr"}, ...]
   ```
4. Ejecuta y visualiza los resultados:
   ```python
   results = run_benchmark(functions, test_cases, iterations=1000)
   print_results(results)
   ```

## Métricas capturadas

- **Tiempo Promedio (s)**: Tiempo de ejecución promediado sobre N iteraciones.
- **Memoria Incremento (MB)**: Incremento en el uso de memoria (RSS) durante la ejecución de la función.
- **Resultado**: El valor retornado por la función (para verificar corrección).
