# 📊 Economic Data Analysis with FRED API

This project utilizes the U.S. Federal Reserve's (FRED) API to extract, analyze, and visualize key economic data, including the S&P 500, the unemployment rate, and the labor participation rate across U.S. states.

## 🚀 Project Features
- **Real-time FRED API Connection** for obtaining up-to-date economic data.
- **Data Extraction and Cleaning** using Pandas.
- **Interactive and Static Visualizations** with Matplotlib and Plotly.
- **Comparison of Unemployment and Labor Participation Rates** across different states.

## 📌 Technologies Used
- Python (Pandas, NumPy, Matplotlib, Plotly)
- FRED API for obtaining economic data
- Kaggle Secrets for securely managing API credentials

## 📥 Installation and Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/fred-economic-analysis.git
cd fred-economic-analysis
```
### 2️⃣ Install Dependencies
It is recommended to use a virtual environment:
```
pip install -r requirements.txt
```
### 3️⃣ Configure the FRED API Key
Sign up [FRED](https://fred.stlouisfed.org/)
 at and obtain an API key. Then, create a .env file in the root directory:   
 ```
FRED_API_KEY=our_api_key_here
```
### 📊 Project Usage
🔹 Query and Plot the S&P 500
```
from fredapi import Fred
import matplotlib.pyplot as plt
import os

fred = Fred(api_key=os.getenv('FRED_API_KEY'))
sp500 = fred.get_series(series_id='SP500')
sp500.plot(figsize=(10, 5), title='S&P 500', lw=2)
plt.show()
```
![image](https://github.com/user-attachments/assets/56e4cc82-9572-430b-a1a3-945b01ca64cd)

### 🔹 Analyze the Unemployment Rate by State
```python
unemp_df = fred.search('unemployment rate state', filter=('frequency', 'Monthly'))
unemp_df = unemp_df.query('seasonal_adjustment == "Seasonally Adjusted" and units == "Percent"')
print(unemp_df.head())
```
### 🔹 Comparison: Unemployment vs. Labor Participation
```python
import plotly.express as px
px.line(uemp_states, title='Tasa de Desempleo por Estado')
```


### 📈 Results and Analysis
- **Historical evolution of the S&P 500 over time.** 
- **Comparison of unemployment rates between states** during the 2020 crisis.
- **Relationship between labor participation and unemployment** across different periords


### 🏆 Contribution
Contributions to improve this project are welcome via pull requests! 😊






----------------------------------------------------------------------------











## 📊 Análisis de Datos Económicos con FRED API

Este proyecto utiliza la API de la Reserva Federal de EE.UU. (FRED) para extraer, analizar y visualizar datos económicos clave, incluyendo el S&P 500, la tasa de desempleo y la tasa de participación laboral en los estados de EE.UU.

## 🚀 Características del Proyecto
- **Conexión con la API de FRED** para obtener datos económicos en tiempo real.
- **Extracción y limpieza de datos** usando Pandas.
- **Visualización interactiva y estática** con Matplotlib y Plotly.
- **Comparación de tasas de desempleo y participación laboral** entre distintos estados.

## 📌 Tecnologías Utilizadas
- Python (Pandas, NumPy, Matplotlib, Plotly)
- FRED API para obtención de datos económicos
- Kaggle Secrets para manejar credenciales de API de forma segura

## 📥 Instalación y Configuración
### 1️⃣ Clonar el Repositorio
```bash
git clone https://github.com/tu-usuario/fred-economic-analysis.git
cd fred-economic-analysis
```

### 2️⃣ Instalar Dependencias
Se recomienda usar un entorno virtual:
```bash
pip install -r requirements.txt
```

### 3️⃣ Configurar la Clave de API de FRED
Regístrate en [FRED](https://fred.stlouisfed.org/) y obtén una clave API. Luego, crea un archivo `.env` en el directorio raíz:
```
FRED_API_KEY=tu_clave_aqui
```

O, si usas Kaggle, almacénala en `kaggle_secrets`.

## 📊 Uso del Proyecto
### 🔹 Consultar y Graficar el S&P 500
```python
from fredapi import Fred
import matplotlib.pyplot as plt
import os

fred = Fred(api_key=os.getenv('FRED_API_KEY'))
sp500 = fred.get_series(series_id='SP500')
sp500.plot(figsize=(10, 5), title='S&P 500', lw=2)
plt.show()
```
![image](https://github.com/user-attachments/assets/56e4cc82-9572-430b-a1a3-945b01ca64cd)

### 🔹 Analizar la Tasa de Desempleo por Estado
```python
unemp_df = fred.search('unemployment rate state', filter=('frequency', 'Monthly'))
unemp_df = unemp_df.query('seasonal_adjustment == "Seasonally Adjusted" and units == "Percent"')
print(unemp_df.head())
```

### 🔹 Comparación: Desempleo vs. Participación Laboral
```python
import plotly.express as px
px.line(uemp_states, title='Tasa de Desempleo por Estado')
```

## 📈 Resultados y Análisis
- **Evolución del S&P 500** a lo largo del tiempo.
- **Comparación del desempleo entre estados** durante la crisis de 2020.
- **Relación entre participación laboral y desempleo** en distintos períodos.

## 🚀 Mejoras Futuras
✅ Integrar dashboards interactivos con **Dash o Streamlit**.
✅ Incorporar más indicadores económicos (inflación, PIB, etc.).
✅ Exportar los análisis a formatos CSV o Power BI.

## 🏆 Contribución
Si quieres mejorar este proyecto, ¡las PRs son bienvenidas! 😊

---
