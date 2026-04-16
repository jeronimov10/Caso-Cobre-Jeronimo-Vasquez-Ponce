# Caso Cobre — Transaction Corridor Analysis
**Jerónimo Vásquez Ponce | Business Architect Assessment | Abril 2026**

---

## Descripción

Análisis de 50,000 transacciones de pagos cross-border procesadas por Cobre
en un período de 6 meses (julio–diciembre 2025), distribuidas en 5 corredores
de pago entre Estados Unidos, México y Colombia.

El proyecto responde tres preguntas de negocio:
- **Parte 1:** Análisis exploratorio de corredores, comportamiento de usuarios y patrones de tiempo.
- **Parte 2:** Investigación de la alta tasa de falla en el corredor USD_MXN (18.25%) y estimación del impacto en revenue.
- **Parte 3:** Recomendación estratégica del corredor a priorizar para inversión en 2026.

---

## Estructura del proyecto

```
├── Caso.ipynb                         # Notebook principal con todo el análisis
├── data/
│   ├── transactions.csv               # 50,000 transacciones (6 meses)
│   └── users.csv                      # 5,000 usuarios únicos
├── entregables/
│   ├── Parte_2_Analisis_Causas.md     # Write-up causas raíz USD_MXN (250-300 palabras)
│   └── Parte_3_Estrategia_Negocio.md  # Memo estratégico corredor a priorizar (400 palabras)
├── Uso_de_IA.md                       # Documentación del uso de herramientas de IA
└── README.md
```

---

## Requisitos

- Python 3.9+
- pandas
- numpy
- matplotlib
- seaborn

Instalación de dependencias:

```bash
pip install pandas numpy matplotlib seaborn
```

---

## Instrucciones de ejecución

1. Clonar o descargar el repositorio.
2. Verificar que los archivos `data/transactions.csv` y `data/users.csv` estén presentes.
3. Abrir `Caso.ipynb` en Jupyter Notebook o JupyterLab.
4. Ejecutar las celdas en orden secuencial (Kernel > Restart & Run All).

```bash
jupyter notebook Caso.ipynb
```

---

## Hallazgos principales

- **Corredor dominante:** USD_MXN concentra el 34.8% del volumen y $85,263 USD de revenue mensual.
- **Problema crítico:** USD_MXN tiene una tasa de falla del 18.25%, cuatro veces el promedio del resto (4.92%).
- **Oportunidad:** Reducir la falla al 5% recuperaría $15,307 USD mensuales adicionales (+18% revenue del corredor).
- **Comportamiento de usuarios:** México y Colombia se comportan de manera casi idéntica; la segmentación por tipo de cliente (enterprise/SME/retail) es más relevante que la geográfica.
- **Patrones de tiempo:** Volumen estable y plano en el período. Pico de actividad a las 10am en días laborales.
