# Matriz de Pendientes — AHP CENEPRED

Herramienta interactiva para el cálculo de la **Matriz de Pendientes** aplicando el **Proceso Analítico Jerárquico (AHP)** de Thomas L. Saaty, siguiendo la metodología del **CENEPRED** (Centro Nacional de Estimación, Prevención y Reducción del Riesgo de Desastres).

> **Demo:** <https://divor.github.io/geo_pendientes/>

## Características

- Matriz de comparaciones pareadas **5×5** (PN1–PN5) con escala de Saaty (1, 3, 5, 7, 9 / 1/X)
- Visualización interactiva de pendientes con gráficos de ángulo (canvas)
- Control deslizante para explorar rangos de pendiente en grados
- Cálculo automático de:
  - Matriz normalizada
  - Vector de pesos (Wi) — prioridades relativas
  - Lambda max (λ), Índice de Consistencia (IC)
  - Razón de Consistencia (RC) con evaluación RC < 10%
- Exportación a **Excel** (`.xls`) con reporte completo (valores decimales)
- Interfaz responsive, sin dependencias externas (HTML + CSS + JS vanilla)

## Metodología

El AHP descompone el problema en una jerarquía y utiliza comparaciones pareadas para determinar la importancia relativa de cada factor. En este caso, se comparan 5 categorías de pendiente:

| Código | Rango | Descripción |
|--------|-------|-------------|
| PN1 | 0–5° | Llano / muy suave |
| PN2 | 5–15° | Suave |
| PN3 | 15–25° | Moderado |
| PN4 | 25–45° | Fuerte |
| PN5 | >45° | Muy fuerte / escarpado |

### Escala de Saaty

| Valor | Significado |
|-------|-------------|
| 1 | Igual peligrosidad |
| 3 | Ligeramente más peligroso |
| 5 | Fuertemente más peligroso |
| 7 | Demostrablemente más peligroso |
| 9 | Absolutamente más peligroso |
| 1/X | Menos peligroso (recíproco) |

### Control de Consistencia

- **RC < 10%** → Matriz válida (juicios consistentes)
- **RC ≥ 10%** → Revisar juicios (inconsistencia)

## Uso

1. Abre `index.html` en cualquier navegador moderno
2. Haz clic en una celda del triángulo superior de la matriz
3. Usa el panel lateral para ajustar el valor de comparación
4. Los resultados se actualizan automáticamente
5. Exporta a Excel con el botón correspondiente

## Despliegue

El proyecto se despliega automáticamente a **GitHub Pages** mediante GitHub Actions al hacer push a `main`/`master`. Ver [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).

## Tecnologías

- HTML5 + CSS3 (Grid, Flexbox, variables)
- JavaScript (ES6+)
- Canvas API para visualización de pendientes
- Sin frameworks ni librerías externas

## Licencia

MIT
