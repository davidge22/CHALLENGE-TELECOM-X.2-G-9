# Telecom X - Análisis de Evasión de Clientes

Este proyecto lo desarrollé para analizar el comportamiento de abandono de clientes (churn) en una empresa de telecomunicaciones. A partir de un dataset realista, busqué identificar patrones y variables clave que puedan ayudar a la empresa a anticipar la pérdida de usuarios y tomar decisiones estratégicas.

## 📥 Extracción de Datos

Primero, realicé la carga de datos directamente desde un archivo JSON alojado en GitHub. Para ello utilicé requests junto con pandas, "https://raw.githubusercontent.com/sthemonica/alura-voz/refs/heads/main/Dados/Telco-Customer-Churn.json".

## 🧹 Transformación de Datos

Después de importar el dataset en formato JSON, identifiqué que varias columnas estaban estructuradas como diccionarios anidados. Para poder analizarlas de forma efectiva, aplané estos campos y los convertí en columnas individuales utilizando herramientas de pandas. 

Posteriormente realicé una limpieza completa sobre el dataframe, que incluyó:

1. Conversión de la columna Charges.Total a tipo numérico (float), ya que originalmente estaba en formato object.

2. Identificación de valores nulos reales en Charges.Total (11 registros), los cuales podrían deberse a errores de entrada o clientes nuevos sin cobros acumulados. Por ahora los mantengo para análisis posterior.

3. Verificación de valores únicos y atípicos en columnas categóricas como Contract, InternetService, PaymentMethod, entre otras.

4. Validación de consistencia en la columna Churn, asegurando que no existan valores vacíos o desconocidos.

5. Se creó una nueva columna llamada **`Cuentas_Diarias`**, calculada a partir del valor mensual de facturación (`Charges.Monthly`). Esta columna representa una estimación del valor diario facturado por cada cliente y se obtiene dividiendo el valor mensual entre 30 días
 

Estas transformaciones dejaron el dataset listo para el análisis exploratorio.

## 📈 Análisis Exploratorio (EDA)

### 📊 Análisis Descriptivo

Se realizó un análisis descriptivo de las principales variables del dataset para comprender mejor el comportamiento de los clientes.

#### 🔢 Variables Numéricas

Se calcularon las siguientes métricas para columnas como `tenure`, `Charges.Monthly`, `Charges.Total` y `Cuentas_Diarias`:

- **Media**
- **Mediana**
- **Desviación estándar**
- **Valor mínimo y máximo**
- **Percentiles**

Este análisis permitió identificar:
- Clientes con altos montos facturados diariamente.
- Casos con poca antigüedad pero alta facturación.
- Alta dispersión en las tarifas mensuales y totales.

#### 🧮 Variables Categóricas

Se analizaron frecuencias de variables como:

- `gender`
- `InternetService`
- `Contract`
- `Churn`



## 🔧 Requisitos

- Python 3.x
- Pandas
- Matplotlib / Seaborn
- Google Colab (recomendado para ejecución)

## 🚀 Instrucciones

1. Clona el repositorio.
2. Abre `Challenge Telecom X.ipynb` en Google Colab.
3. Ejecuta las celdas para ver el análisis completo y visualizaciones.

## 👤 Autor

David Alonso García Espichán
Ing. Civil 
Parte del Programa ONE de Alura Latam G-9

