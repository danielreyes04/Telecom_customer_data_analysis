# 📡 Telecom Customer Churn — Análisis Exploratorio

Análisis exploratorio de datos para identificar qué variables influyen en que un cliente abandone el servicio de una empresa de telecomunicaciones.

---

## 🎯 Objetivo

Determinar qué factores están asociados al **churn** (abandono del servicio) de clientes, usando pruebas estadísticas y visualizaciones que permitan priorizar variables para modelos predictivos o estrategias de retención.

---

## 📂 Dataset

**Archivo:** `telecom_customer_churn_feature_engineering.csv`  
**Registros:** 1.200 clientes  
**Variable objetivo:** `churn` (0 = permanece, 1 = abandona)

| Variable | Tipo | Descripción |
|---|---|---|
| `customer_id` | ID | Identificador único |
| `age` | Numérica | Edad del cliente |
| `gender` | Categórica | Género |
| `city` | Categórica | Ciudad de residencia |
| `education_level` | Categórica | Nivel educativo |
| `employment_status` | Categórica | Estado de empleo |
| `monthly_income` | Numérica | Ingreso mensual estimado |
| `monthly_bill` | Numérica | Factura mensual |
| `internet_usage_gb` | Numérica | Uso de internet en GB |
| `call_minutes` | Numérica | Minutos de llamadas al mes |
| `contract_type` | Categórica | Tipo de contrato (Monthly / 6-Month / 12-Month) |
| `support_tickets` | Numérica | Tickets de soporte creados |
| `customer_feedback` | Categórica | Calificación del servicio |
| `churn` | Binaria | 1 = abandonó, 0 = activo |


---

## 📊 Resultados por variable

| Variable | Prueba | Resultado | ¿Influye en el churn? |
|---|---|---|---|
| `city` | Chi² | p = 0.626 | No significativa |
| `employment_status` | Chi² | p > 0.05 |  No significativa |
| `call_minutes` | Cohen's d | d = 0.096 (efecto mínimo) |  No relevante |
| `customer_feedback` | Chi² | p > 0.05 |  No significativa |
| `monthly_income` | Boxplot + medias | Diferencia leve |  Indicio débil |
| `contract_type` | Chi² | p = 1.55e-27 |  **Muy significativa** |

---

## 💡 Hallazgo principal

> El **tipo de contrato** es la variable más influyente en el churn.

Los clientes con contrato **mensual** representan la gran mayoría de los abandonos (296 de 420 churns totales), mientras que quienes tienen contratos de 6 o 12 meses raramente abandonan el servicio.

| Tipo de contrato | Clientes activos | Clientes que abandonaron |
|---|---|---|
| 12-Month | 284 | 61 |
| 6-Month | 223 | 63 |
| **Monthly** | 273 | **296** |

---

## Recomendación

Incentivar la migración de clientes al plan de **6 o 12 meses**, ya sea mediante:
- Descuentos por compromiso de permanencia
- Promociones de entrada con planes de mayor duración
- Beneficios exclusivos para contratos largos

---

##  Tecnologías

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scipy

---

## Cómo ejecutar

```bash
# 1. Clona el repositorio
git clone https://github.com/tu-usuario/telecom-churn-analysis.git
cd telecom-churn-analysis

# 2. Instala dependencias
pip install pandas numpy matplotlib seaborn scipy jupyter

# 3. Abre el notebook
jupyter notebook Telecom_customer.ipynb
```

---

## 👤 Autor

**Daniel Steven Reyes**  
[GitHub](https://github.com/danielreyes04) 
