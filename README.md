# Lorenz-Attractor-Simulation

# Simulación del Atractor de Lorenz — Euler vs Runge-Kutta 4

Simulación y visualización 3D del **atractor de Lorenz**, un sistema dinámico caótico, comparando la precisión de dos métodos numéricos: **Euler** y **Runge-Kutta de 4to orden (RK4)**.

## ¿Qué es el atractor de Lorenz?

El sistema de Lorenz es un conjunto de tres ecuaciones diferenciales ordinarias propuesto por Edward Lorenz en 1963 para modelar convección atmosférica:

```
dx/dt = σ(y - x)
dy/dt = x(ρ - z) - y
dz/dt = xy - βz
```

Con los parámetros clásicos `σ=10`, `ρ=28`, `β=8/3`, el sistema exhibe **comportamiento caótico**: trayectorias que nunca se repiten exactamente y son extremadamente sensibles a las condiciones iniciales (el famoso "efecto mariposa").

## Métodos numéricos implementados

### Método de Euler
Aproximación de primer orden. Simple pero acumula error rápidamente en sistemas caóticos.

```python
x_new = x + h * dx
```

### Runge-Kutta de 4to orden (RK4)
Aproximación de cuarto orden. Evalúa la derivada en 4 puntos intermedios por paso, resultando en una trayectoria mucho más precisa.

```python
x_new = x + (h/6) * (k1 + 2*k2 + 2*k3 + k4)
```

## Comparación de resultados

La visualización 3D muestra cómo ambos métodos divergen con el tiempo, ilustrando la sensibilidad del sistema caótico al método de integración utilizado. RK4 mantiene la forma característica del atractor por más tiempo antes de acumular error significativo.

| Parámetro | Valor |
|-----------|-------|
| Paso de tiempo (h) | 0.01 |
| Pasos simulados | 10,000 |
| Condiciones iniciales | (1.0, 1.0, 1.0) |

## Tecnologías

- Python 3
- NumPy
- Matplotlib (visualización 3D)

## ¿Por qué es relevante para datos e IA?

Los sistemas caóticos aparecen en predicción financiera, modelado de series de tiempo y simulaciones. Entender métodos numéricos como RK4 es base para implementar soluciones de ML que involucran ecuaciones diferenciales (Neural ODEs, por ejemplo).
