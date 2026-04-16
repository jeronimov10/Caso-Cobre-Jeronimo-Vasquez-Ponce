# Análisis de Fallas: Corredor USD_MXN
**Jerónimo Vásquez Ponce — Cobre Business Architect Assessment**

---

El corredor USD_MXN es el más relevante de la plataforma (34.8% del volumen total),
pero su tasa de falla del 18.25% cuadruplica el promedio del resto de corredores (4.92%),
representando una fuga crítica de ingresos que requiere atención inmediata.

## Patrones identificados

El análisis de las 3,177 transacciones fallidas revela tres señales consistentes.
Primero, el segmento enterprise concentra la mayor tasa de falla (23.9%), seguido
de retail (19.5%), mientras que SME es el más estable (14.1%). Segundo, las
transacciones fallidas tienen un ticket promedio superior a las exitosas
($7,902 vs $7,130 USD), lo que vincula directamente el monto de la operación
con la probabilidad de rechazo. Tercero, la distribución de fallas es
completamente uniforme por día de la semana (17–19%) y sin tendencia mensual
clara, lo que descarta problemas de capacidad o eventos puntuales.

## Causas raíz probables

**Causa 1 — Compliance y controles AML:** El sistema SPEI y los bancos mexicanos
exigen metadatos y documentación rigurosa para transferencias de alto valor.
Es posible que Cobre no esté enviando la información requerida, generando
rechazos automáticos por controles anti-lavado de activos.

**Causa 2 — Falla estructural de integración técnica:** La uniformidad temporal
de los errores descarta saturación puntual y apunta a incompatibilidades
persistentes en el formato de mensajes bancarios (ISO 20022), timeouts o
rechazos silenciosos de bancos receptores específicos en México.

**Causa 3 — Perfiles KYC mal configurados en enterprise:** El segmento con mayor
falla (23.9%) puede tener límites operativos, fuentes de fondos o verificaciones
de identidad incompletas para el corredor USD_MXN, generando bloqueos por
reglas internas de riesgo de Cobre o del banco corresponsal.

## Validación y validación recomendada

Auditar los códigos de error de rechazo es el primer paso: errores AML confirman
la Causa 1, errores de formato o timeout confirman la Causa 2, y bloqueos por
perfil de usuario confirman la Causa 3.

## Impacto financiero

Las fallas actuales generan una pérdida de **$21,080 USD mensuales** en revenue.
Reducir la tasa al 5% recuperaría ~385 transacciones por mes, representando
una ganancia adicional de **$15,307 USD mensuales** — un incremento del 18%
en el revenue del corredor más importante de la plataforma.

---
*Fees estimados: 0.5% variable + $0.30 USD fijo por transacción.
Sujeto a estructura real de facturación de Cobre.*
