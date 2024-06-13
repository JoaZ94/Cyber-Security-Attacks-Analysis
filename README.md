# Análisis de Ataques de Ciberseguridad

## Proyecto de Ciencia de Datos

Elaborado por: **José Luis Díaz Torres**

---

## Objetivo

### Objetivo General

Desarrollar un modelo predictivo que pueda determinar el tipo de ataque cibernético basado en las características del tráfico de red e indicadores de seguridad. Utilizando técnicas de clasificación, buscamos identificar patrones y relaciones entre las variables del conjunto de datos que permitan prever el tipo de ataque con alta precisión.

### Objetivos Específicos

- Analizar un dataset relacionado con ataques de ciberseguridad.
- Identificar y predecir tipos de ataques cibernéticos.
- Proporcionar información valiosa para mejorar las estrategias de defensa y mitigación de ataques.

---

## Fuente del Dataset

- **Fuente del Dataset:** [Kaggle - Cyber Security Attacks](https://www.kaggle.com/datasets/teamincribo/cyber-security-attacks)
- **Descripción:** El dataset proporciona una representación realista del historial de actividad en línea para evaluar mapas de calor, firmas de ataque, tipos y más.

---

## Descripción de los Campos del Dataset

El dataset contiene múltiples atributos que describen características de los paquetes de datos y eventos de red:

1. Timestamp
2. Source IP Address
3. Destination IP Address
4. Source Port
5. Destination Port
6. Protocol
7. Packet Length
8. Packet Type
9. Traffic Type
10. Payload Data
11. Malware Indicators
12. Anomaly Scores
13. Alerts/Warnings
14. Attack Type
15. Attack Signature
16. Action Taken
17. Severity Level
18. User Information
19. Device Information
20. Network Segment
21. Geo-location Data
22. Proxy Information
23. Firewall Log

---

## Hipótesis

1. **Relación entre la Información de Red y Tipos de Ataques:** Se espera que la información de red tenga una correlación significativa con tipos específicos de ataques cibernéticos.
2. **Impacto de los Datos de Seguridad y Detección:** La presencia de datos de seguridad y detección se correlacionará fuertemente con ciertos tipos de ataques.
3. **Influencia del Usuario y su Dispositivo:** La información de usuario y su dispositivo puede tener relación directa con el tipo de ataque.
4. **Correlación entre la Información de Red y Localización, y los tipos de Ataques:** Se espera que la información de la red y la localización tengan más relación con ciertos tipos de ataque.
5. **Variación según los indicadores y los tipos de ataque:** Hay algunos indicadores que van a estar presentes en unos tipos de ataque más que en otros.

---

## Procesamiento de Campos

### Campos Eliminados

- **Payload Data:** Unicidad total, no aporta información útil.
- **User Information:** Alta unicidad (> 80%) y referencia a datos personales.
- **Attack Signature:** Hace parte de la variable objetivo.
- **Severity Level:** Indica la severidad del ataque, parte de la variable objetivo.
- **Action Taken:** Consecuencia del ataque detectado, no predictivo.

### Campos Procesados

- **Campos con vacíos diligenciados:** Malware Indicators, Alerts/Warnings, Firewall Logs, IDS/IPS Alerts.
- **Generación de Nuevos Campos:**
  - **Day Part:** Early Morning, Morning, Afternoon, Night.
  - **Day Of Week:** 0 (Lunes) a 6 (Domingo).
  - **Source IP Class y Destination IP Class:** Clase A, B, C.
  - **Source Port Category y Destination Port Category:** Well-known Port, Registered Port, Dynamic Port.
  - **Browser y Operating System:** Mozilla, Opera, Android, iOS, Linux, Mac OS, Windows.
  - **State:** Estado basado en Geo-location Data.
  - **Proxy Indicator:** Indica si se usó un Proxy.

### Dataframe Final

- El dataframe final se generó después de procesar y eliminar los campos no útiles.

---

## Análisis Exploratorio de Datos (EDA)

Se realizó un análisis exploratorio por cada hipótesis, incluyendo:

- **Análisis Univariado**
- **Análisis Bivariado**
- **Análisis Multivariado**
- Visualizaciones y técnicas como Mapas de Calor de Correlación, Countplot, Histograma, Boxplot, Violinplot, Scatterplot, Pairplot.

---

## Conclusiones

1. **Relación entre la Información de Red y Tipos de Ataques:**
   - No se evidencia una relación directa significativa entre las features y el Label, salvo entre Packet Type y Attack Type.

2. **Impacto de los Datos de Seguridad y Detección:**
   - Distribución de frecuencia similar a una distribución rectangular.

3. **Influencia del Usuario y su Dispositivo:**
   - Desbalanceo evidente en los sistemas operativos más usados.

4. **Correlación entre la Información de Red y Localización, y los tipos de Ataques:**
   - Balance de datos en su totalidad.
   
5. **Variación según los indicadores y los tipos de ataque:**
   - Balance de datos en su totalidad.

**Otras Conclusiones:**

- La variable de salida (Attack Type) está balanceada.
- Se utilizó un gráfico de recuento para variables categóricas.

---

Para más detalles, consulta el archivo del proyecto (PDF) y el notebook con el análisis completo.
