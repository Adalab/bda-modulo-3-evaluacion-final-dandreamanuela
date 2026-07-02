# Análisis del Programa de Fidelización de Clientes de una Aerolínea

## Descripción del proyecto

Este proyecto corresponde al **ejercicio de evaluación final del Módulo 3 de Data Analytics**. El objetivo es realizar un **Análisis Exploratorio de Datos (EDA)** sobre dos conjuntos de datos pertenecientes al programa de fidelización de una aerolínea, con el fin de obtener información relevante sobre el comportamiento de los clientes y su actividad de vuelo.

El proyecto incluye la limpieza y preparación de los datos, el análisis estadístico de variables numéricas y categóricas, la creación de visualizaciones y el análisis de las diferencias en las reservas de vuelos según el nivel educativo de los clientes.

---

## Conjunto de datos

El análisis se realiza a partir de dos archivos CSV.

### Customer Flight Analysis

Contiene información sobre la actividad mensual de vuelo de los clientes, incluyendo:

* Identificador del cliente (`Loyalty Number`)
* Año y mes de la actividad
* Número de vuelos reservados
* Vuelos realizados con acompañantes
* Número total de vuelos
* Distancia recorrida
* Puntos acumulados
* Puntos canjeados
* Coste en dólares de los puntos canjeados

### Customer Loyalty History

Contiene información demográfica y del programa de fidelización de cada cliente, incluyendo:

* País, provincia y ciudad de residencia
* Código postal
* Género
* Nivel educativo
* Salario
* Estado civil
* Tipo de tarjeta de fidelización
* Customer Lifetime Value (CLV)
* Tipo de inscripción en el programa
* Fecha de inscripción
* Fecha de cancelación (cuando aplica)

Ambos conjuntos de datos se unieron mediante la columna **`Loyalty Number`**, que actúa como identificador único del cliente.

---

## Objetivos

* Explorar la estructura y calidad de los datos.
* Detectar y tratar valores nulos y duplicados.
* Unificar y preparar ambos conjuntos de datos para su análisis.
* Obtener estadísticas descriptivas de las variables numéricas.
* Analizar la distribución de las variables categóricas.
* Identificar posibles valores atípicos.
* Estudiar la correlación entre variables numéricas.
* Responder preguntas de negocio mediante visualizaciones.
* Analizar las diferencias en el número de vuelos reservados según el nivel educativo de los clientes.

---

## Fases del proyecto

### Fase 1. Exploración y limpieza de datos

* Exploración inicial de ambos datasets.
* Revisión de la estructura de los datos.
* Identificación de valores nulos y registros duplicados.
* Unión de ambos conjuntos de datos.
* Tratamiento de valores faltantes.
* Conversión de tipos de datos.
* Verificación de la consistencia de la información.

Acciones de limpieza implementadas:

* Convertir "Points Accumulated" a int64
* Revisar duplicados que pero no se pueden borrar ya que corresponden a distintos vuelos realizados en diferentes meses por un mismo cliente
* Revisar nulos de las categorias Salary, Cancellation Year y Cancellation Month: no los puedo convertir a texto porque son variables numéricas
* Convertir Cancellation Year y Cancellation Month de datos de tipo float a int64

---

### Fase 2. Análisis estadístico

#### Variables numéricas

Se calcularon diferentes estadísticas descriptivas:

* Media
* Mediana
* Moda
* Desviación estándar
* Varianza
* Valor mínimo, valor máximo y rango

Además, se realizó:

* Detección de valores atípicos mediante el método del rango intercuartílico (IQR).
* Análisis de correlación entre variables numéricas.

#### Variables categóricas

Se analizaron las distribuciones de frecuencia absoluta y relativa de las principales variables categóricas, acompañadas de una interpretación de los resultados.

---

### Fase 3. Visualización de datos

Se desarrollaron diferentes visualizaciones para responder a las siguientes preguntas:

* ¿Cómo se distribuye la cantidad de vuelos reservados por mes durante el año?
* ¿Existe una relación entre la distancia recorrida y los puntos acumulados?
* ¿Cuál es la distribución de los clientes por provincia?
* ¿Cómo varía el salario promedio según el nivel educativo?
* ¿Cuál es la proporción de clientes según el tipo de tarjeta de fidelización?
* ¿Cómo se distribuyen los clientes según su estado civil y género?

Cada gráfico incluye una breve interpretación orientada a facilitar la comprensión de los resultados.

---

### Fase 4. Evaluación de diferencias según el nivel educativo

Se estudió si existían diferencias en el número de vuelos reservados según el nivel educativo de los clientes.

Para ello se realizó:

* Selección de las variables **`Flights Booked`** y **`Education`**.
* Cálculo de estadísticas descriptivas por nivel educativo.
* Comparación del comportamiento de los distintos grupos.

---

## Tecnologías utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

---

## Competencias desarrolladas

* Limpieza y preparación de datos.
* Integración de múltiples fuentes de información.
* Análisis exploratorio de datos (EDA).
* Estadística descriptiva.
* Identificación de valores atípicos.
* Análisis de correlación.
* Visualización de datos.
* Interpretación y comunicación de resultados.

---

## Estructura del repositorio

```text
├── data/
│   ├── Customer Flight Analysis.csv
│   └── Customer Loyalty History.csv
├── notebooks/
│   └── Analisis_Programa_Fidelizacion_Aerolinea.ipynb
├── images/
│   └── graficos/
├── README.md
```

---

## Conclusión

Este proyecto permitió aplicar el flujo completo de un análisis exploratorio de datos utilizando información real de un programa de fidelización de clientes. A través de la limpieza, transformación y análisis de los datos, fue posible extraer información relevante sobre el comportamiento de los clientes y responder a diferentes preguntas de negocio mediante técnicas estadísticas y visualizaciones.
