# 🚴 Predicción de Demanda en Sistema de Alquiler de Bicicletas

## 📋 Descripción del Proyecto

Este proyecto aplica técnicas de **regresión polinomial** para construir un modelo predictivo que estima la demanda de un sistema de alquiler de bicicletas. El objetivo principal es identificar los factores que más inciden en la demanda y desarrollar un modelo preciso siguiendo el ciclo completo de Machine Learning.

## 🎯 Objetivos

- Predecir la demanda de bicicletas (`cnt`) basándose en variables climáticas y temporales
- Identificar los factores más relevantes que afectan la demanda
- Comparar modelos de regresión polinomial de diferentes grados
- Seleccionar el modelo con mejor rendimiento predictivo

## 📊 Dataset

El dataset `Datos_Etapa-1.csv` contiene información sobre el uso del sistema de alquiler de bicicletas con las siguientes variables:

### Variables Categóricas
- `season`: Estación del año (Winter, Spring, Summer, Fall)
- `weathersit`: Condición climática (Clear, Mist, etc.)
- `time_of_day`: Momento del día (Night, Morning, Afternoon, Evening)
- `weekday`: Día de la semana (0-6)

### Variables Numéricas
- `temp`: Temperatura
- `atemp`: Sensación térmica
- `hum`: Humedad
- `windspeed`: Velocidad del viento

### Variable Objetivo
- `cnt`: Cantidad de bicicletas alquiladas (demanda)

## 🔧 Tecnologías Utilizadas

- **Python 3.x**
- **pandas**: Manipulación de datos
- **scikit-learn**: Modelos de ML y preprocesamiento
- **numpy**: Operaciones numéricas

### Librerías principales
```python
pandas
scikit-learn
numpy
```

## 📁 Estructura del Proyecto
```
├── data/
│   └── Datos_Etapa-1.csv
├── notebooks/
│   └── modelo_regresion.ipynb
├── README.md
└── requirements.txt
```

## 🚀 Pipeline de Machine Learning

### 1. Carga y Exploración de Datos
- Carga del dataset desde CSV
- Análisis estadístico descriptivo con `describe()`

### 2. Limpieza de Datos
- Identificación de valores faltantes
- Detección y eliminación de duplicados

### 3. Preprocesamiento
- **Codificación de variables categóricas**: One-Hot Encoding para `season`, `weathersit`, `time_of_day`
- **Normalización**: RobustScaler para estandarizar variables numéricas
- **División de datos**: 80% entrenamiento, 20% prueba

### 4. Ingeniería de Features
- Generación de características polinomiales (grado 2 y 3)
- Creación de términos de interacción entre variables

### 5. Entrenamiento de Modelos
- **Modelo 1**: Regresión Polinomial Grado 2
- **Modelo 2**: Regresión Polinomial Grado 3

### 6. Evaluación
Métricas utilizadas:
- **RMSE** (Root Mean Squared Error): Error promedio
- **MAE** (Mean Absolute Error): Error absoluto promedio
- **R²** (Coeficiente de determinación): Varianza explicada

## 📈 Resultados

| Modelo | RMSE | Mejor Modelo |
|--------|------|--------------|
| Polinomial Grado 2 | 135.96 | ❌ |
| Polinomial Grado 3 | 132.31 | ✅ |

### Conclusión

El **modelo polinomial de grado 3** fue seleccionado como modelo final debido a:
- Menor error de predicción (RMSE: 132.31)
- Mejor captura de patrones no lineales
- Equilibrio óptimo entre complejidad y rendimiento

## 🔍 Hallazgos Clave

El modelo permite identificar cómo factores como la estación del año, condiciones climáticas y momento del día influyen en la demanda de bicicletas, proporcionando insights valiosos para la gestión del sistema de alquiler.

## 💻 Uso

1. Clonar el repositorio:
```bash
git clone [URL_DEL_REPOSITORIO]
cd [NOMBRE_DEL_REPOSITORIO]
```

2. Instalar dependencias:
```bash
pip install -r requirements.txt
```

3. Ejecutar el notebook:
```bash
jupyter notebook notebooks/modelo_regresion.ipynb
```

## 📝 Notas

- Se utiliza `RobustScaler` por su resistencia a valores atípicos
- `random_state=77` asegura reproducibilidad de resultados
- One-Hot Encoding con `drop_first=True` evita multicolinealidad

## 👥 Autor

[Tu Nombre]

## 📄 Licencia

[Especificar licencia si aplica]