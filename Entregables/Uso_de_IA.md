# Uso de Herramientas de IA
**Caso Cobre — Jerónimo Vásquez Ponce**

---

## Herramientas utilizadas

### Claude Code (Anthropic)
Utilizado como asistente principal a lo largo de todo el proyecto mediante
la interfaz de línea de comandos integrada en el IDE.

### Claude (claude.ai)
Utilizado para investigación, redacción y verificación de contenido.

---

## Para qué se usó cada herramienta

### 1. Optimización de código y visualizaciones

Claude Code asistió en la escritura y depuración de las celdas de análisis,
incluyendo funciones de agregación con pandas, construcción de visualizaciones
con matplotlib y estructuración general del notebook.

Ejemplo de optimización aplicada: durante el análisis de comportamiento por
país y corredor, se aprendió y aplicó el método `.unstack()` para transformar
tablas agrupadas en formato pivot, convirtiendo índices multi-nivel en columnas
legibles. Esto permitió pasar de una serie agrupada por `['country', 'corridor']`
a una tabla comparativa directamente graficable, reduciendo el código necesario
y mejorando la legibilidad del análisis:

```python
# Sin .unstack(): resultado difícil de leer y graficar
df.groupby(['country', 'corridor']).size()

# Con .unstack(): tabla pivot lista para visualizar
df.groupby(['country', 'corridor']).size().unstack(fill_value=0)
```

### 2. Investigación regulatoria y causas de fallo en USD_MXN

Claude asistió en la investigación del marco regulatorio mexicano aplicable
al corredor USD_MXN, incluyendo:
- Funcionamiento del sistema SPEI (Banco de México) y sus requisitos de mensajería.
- Controles AML/KYC exigidos por la CNBV para transferencias de alto valor.
- Estándares de mensajería bancaria internacional (ISO 20022) y causas comunes
  de rechazo en integraciones con bancos receptores mexicanos.
- Estructura de fees de referencia en la industria fintech para corredores
  USD_MXN (variable fee + fixed fee por transacción).

Esta investigación fundamentó las tres hipótesis de causa raíz planteadas
en la Parte 2 del análisis.

### 3. Redacción y formato de entregables

Claude asistió en la redacción del write-up de 250-300 palabras (Parte 2)
y el memorando estratégico de 400 palabras (Parte 3), asegurando que los
argumentos estuvieran fundamentados en los datos calculados en el notebook
y que el tono fuera profesional y orientado a negocio.

### 4. Pruebas y verificación asistida por IA

Claude Code apoyó en la verificación de consistencia entre los valores
calculados en las celdas de código y los números citados en los markdowns,
identificando discrepancias de redondeo y asegurando que todas las métricas
clave (tasas de falla, revenue perdido, ganancia potencial) coincidieran
entre el análisis y los entregables escritos.

---
