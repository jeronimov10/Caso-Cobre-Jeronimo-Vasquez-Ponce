# Análisis de Fallas: Corredor USD_MXN
**Jerónimo Vásquez Ponce — Cobre Business Architect Assessment**

El corredor USD_MXN concentra el 34.8% del volumen, pero su tasa de falla del 18.25% cuadruplica el promedio del resto de corredores (4.92%), representando una fuga crítica de ingresos.

## Patrones identificados

El análisis de las 3,177 transacciones fallidas revela tres señales. Primero, el segmento enterprise tiene la mayor tasa de falla (23.9%), seguido de retail (19.5%) y SME (14.1%). Segundo, las transacciones fallidas tienen ticket promedio superior ($7,902 vs $7,130 USD), vinculando el monto con la probabilidad de rechazo. Tercero, la distribución de fallas es uniforme por día y mes, descartando problemas de capacidad o eventos puntuales.

## Causas raíz probables

**Causa 1 — Compliance AML:** El SPEI exige documentación rigurosa para transferencias de alto valor. Cobre puede no estar enviando los metadatos requeridos, generando rechazos automáticos.

**Causa 2 — Integración técnica:** La uniformidad temporal de los errores apunta a incompatibilidades en mensajería bancaria (ISO 20022) o timeouts con bancos receptores en México.

**Causa 3 — Perfiles KYC enterprise:** El segmento con mayor falla puede tener límites operativos o verificaciones de identidad incompletas para este corredor, generando bloqueos internos.

## Validación

Auditar los códigos de error es el primer paso: errores AML confirman la Causa 1, errores de formato la Causa 2, y bloqueos por perfil la Causa 3.

## Impacto financiero

Las fallas generan una pérdida de **$21,080 USD mensuales**. Reducir la tasa al 5% recuperaría ~385 transacciones por mes y **$15,307 USD mensuales** adicionales, un incremento del 18% en el revenue del corredor más importante de la plataforma.

---
*Fees: 0.5% variable + $0.30 USD fijo por transacción. Sujeto a estructura real de facturación de Cobre.*
