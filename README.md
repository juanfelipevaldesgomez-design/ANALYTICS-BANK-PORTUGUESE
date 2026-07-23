# ANALYTICS-BANK-PORTUGUESE
Análisis exploratorio orientado a negocio sobre una campaña de telemarketing de un banco, con el objetivo de identificar qué perfiles de cliente tienen mayor probabilidad de suscribirse a un depósito a plazo.

Pregunta de negocio

¿Quién es más propenso a suscribirse a un depósito a plazo, y cómo debería el equipo de marketing priorizar sus contactos?

Dataset
Fuente: Bank Marketing Dataset (UCI Machine Learning Repository) — campañas de telemarketing directo de una institución bancaria portuguesa.
Tamaño: 45,211 registros, 17 columnas.
Variable objetivo: subscribed (yes/no) — si el cliente contrató el depósito a plazo.
Tasa de conversión global: 11.7%.


Resumen ejecutivo
El historial con el banco es la señal más fuerte. Clientes con una campaña anterior exitosa convierten al 64.7% (vs. 9.2% en quienes nunca fueron contactados antes) — 7x la tasa base. Representa solo el 3.3% de la base, así que es potente pero de bajo alcance.
Edad y ocupación importan más que el resto de variables demográficas. Clientes de 65+ años convierten al 42.5%, estudiantes al 28.7% — ambos muy por encima del promedio, pese a ser los segmentos más pequeños en volumen.
Menos compromisos financieros = mayor conversión. Clientes sin hipoteca activa convierten más del doble que quienes sí tienen (16.5% vs 7.7%); patrón similar en préstamos personales y default.
Educación terciaria supera a primaria por 6.4 puntos (14.9% vs 8.5%).
El cruce job × education revela combinaciones de alto valor no visibles en el análisis univariado: estudiantes con secundaria (29.7%) y jubilados con terciaria (27.6%) lideran la conversión.

Recomendación: priorizar el recontacto a clientes con historial de campaña exitosa, y diseñar guiones de venta diferenciados para estudiantes y jubilados en vez de un enfoque genérico — estos segmentos, aunque pequeños, tienen el mayor retorno por contacto.

Metodología
Renombrado de columnas genéricas (V1-V16) a nombres descriptivos según el diccionario oficial del dataset.
Corrección de la codificación de la variable objetivo.
Tratamiento de pdays = -1 como categoría propia ("nunca contactado antes"), no como dato faltante.
Creación de grupos de edad para capturar relaciones no lineales.
Cálculo de tasa de conversión por segmento, filtrando grupos con menos de 50-100 observaciones para evitar ruido estadístico.
Todas las comparaciones se hacen contra la tasa base (11.7%) como referencia visual en cada gráfico.

Estructura del repositorio
├── bank_marketing_analysis.ipynb   # Notebook completo con EDA y gráficos
├── Bank_marketing_Dataset.csv      # Dataset original
├── images/                         # Gráficos exportados
└── README.md


Cómo correrlo
bash
pip install pandas seaborn matplotlib
jupyter notebook bank_marketing_analysis.ipynb


Herramientas

Python · Pandas · Seaborn · Matplotlib
