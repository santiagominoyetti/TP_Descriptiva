# TP_Descriptiva
# Análisis Profundo del Ecosistema Google Play Store: Factores de Éxito y Modelos Predictivos

## Descripción General del Proyecto

El mercado de aplicaciones móviles, con Google Play Store como uno de sus principales exponentes, es un ecosistema vasto y dinámico. Para desarrolladores, marketers e inversores, comprender los factores que impulsan el éxito de una aplicación —ya sea en términos de popularidad, satisfacción del usuario o viabilidad comercial— es crucial para la toma de decisiones estratégicas.

Este proyecto se sumerge en un extenso conjunto de datos de Google Play Store para descubrir patrones, validar supuestos y construir modelos predictivos que ofrezcan insights accionables. El objetivo principal es **identificar las características clave de las aplicaciones y las dinámicas del mercado que influyen en su rendimiento (medido por instalaciones y ratings) y explorar la viabilidad de predecir ciertos atributos de las aplicaciones, con el fin de orientar estrategias de desarrollo, monetización y marketing más efectivas.**

## Variables Clave Analizadas

El análisis se centra en un conjunto rico de variables, entre las que destacan:

* **Identidad y Contenido de la App:**
    * `App Name`: Identificador de la aplicación.
    * `Category` (y la derivada `Category_General`): La categoría principal a la que pertenece la app (ej. Juegos, Productividad, Estilo de Vida).
    * `Content Rating` (y la derivada `Min_Age`): La clasificación de edad para la que es adecuada la app.
* **Métricas de Rendimiento y Popularidad:**
    * `Rating`: La calificación promedio otorgada por los usuarios.
    * `Rating Count` (y `Rating_Count_log`): El número total de valoraciones recibidas.
    * `Maximum Installs` (y `max_installs_log`): El número máximo de instalaciones alcanzadas (variable objetivo principal para regresión).
* **Características y Monetización:**
    * `Size` (y `Size_log`): El tamaño de la aplicación.
    * `Price`: El precio de la aplicación (0 si es gratuita).
    * `In App Purchases`: Indicador de si la app ofrece compras dentro de la aplicación.
    * `Ad Supported`: Indicador de si la app muestra publicidad.
    * `Editors Choice`: Indicador de si la app fue seleccionada como "Editor's Choice".
* **Ciclo de Vida y Actividad:**
    * `Last Updated` (y las derivadas `Active_Life_log`, `Inactive_Time_log`): Indicadores de cuán recientemente se actualizó la app y su tiempo de vida activa.
* **Segmentación:**
    * `Cluster_Label`: Etiqueta de cluster asignada mediante K-Means para segmentar las aplicaciones.
* **Target para Clasificación:**
    * `No_Ratings` (derivada como `is_No_Ratings`): Variable binaria para predecir si una app no ha recibido suficientes ratings o ninguno.

## Objetivos Específicos y Enfoque Analítico

El proyecto aborda sus objetivos mediante:

1.  **Análisis Exploratorio de Datos (EDA):** Para comprender las distribuciones, relaciones y patrones iniciales en los datos.
2.  **Limpieza y Preprocesamiento Exhaustivo:** Manejo de valores faltantes, transformación de tipos, ingeniería de características (como `Category_General`, `Min_Age`, variables logarítmicas) y escalado/codificación para preparar los datos para el modelado.
3.  **Modelado Predictivo:**
    * **Regresión:** Para predecir `max_installs_log` utilizando modelos como RandomForestRegressor y XGBoostRegressor.
    * **Clasificación:** Para predecir `is_No_Ratings` utilizando Regresión Logística.
