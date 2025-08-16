# 🚖 Análisis de Datos de Zuber en Chicago  

**Zuber** es una nueva empresa de viajes compartidos que busca posicionarse en Chicago, una ciudad con un mercado altamente competitivo.  
El objetivo de este proyecto es analizar información disponible sobre los viajes y las condiciones externas que los afectan, con el fin de identificar patrones en el comportamiento de los usuarios y generar información útil para la toma de decisiones estratégicas.  

---

## 📊 Contexto del Estudio  
- Se exploraron bases de datos con información de viajes en taxi en Chicago.  
- Se incluyeron datos de barrios, vehículos, trayectos y registros meteorológicos.  
- También se revisaron datos de empresas competidoras para comparar tendencias.  

Este análisis permitió formular y comprobar hipótesis sobre la relación entre las condiciones climáticas y la demanda de viajes.  

---

## 🗂️ Estructura de los Datos  

### `neighborhoods`  
Datos sobre los barrios de la ciudad.  
- `name` — nombre del barrio.  
- `neighborhood_id` — identificador del barrio.  

### `cabs`  
Información de los taxis.  
- `cab_id` — código del vehículo.  
- `vehicle_id` — identificador técnico del vehículo.  
- `company_name` — empresa propietaria del vehículo.  

### `trips`  
Detalles de los viajes realizados.  
- `trip_id` — identificador del viaje.  
- `cab_id` — vehículo que opera el viaje.  
- `start_ts` — fecha y hora de inicio (redondeada a la hora).  
- `end_ts` — fecha y hora de finalización (redondeada a la hora).  
- `duration_seconds` — duración en segundos.  
- `distance_miles` — distancia en millas.  
- `pickup_location_id` — barrio de recogida.  
- `dropoff_location_id` — barrio de destino.  

### `weather_records`  
Registros meteorológicos.  
- `record_id` — identificador del registro.  
- `ts` — fecha y hora (redondeada a la hora).  
- `temperature` — temperatura registrada.  
- `description` — descripción breve, p. ej. *“lluvia ligera”* o *“nubes dispersas”*.  

---

## 🔎 Metodología  

1. **Obtención de datos meteorológicos:**  
   Los registros se descargaron desde la página [Chicago Weather 2017](https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html) utilizando `requests` y `BeautifulSoup` (`bs4`).  

2. **Consulta y limpieza de datos:**  
   - Se ejecutaron consultas SQL sobre la base de datos de taxis en Chicago.  
   - Los resultados fueron almacenados en archivos `.csv`.  

3. **Análisis exploratorio:**  
   - Procesamiento de datos con `pandas`.  
   - Visualización de resultados con `matplotlib.pyplot`.  

---

## 📐 Hipótesis  

**Hipótesis de trabajo:**

*"La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare cambia los sábados lluviosos".*

- **Hipótesis Nula (H₀):** La duración promedio de los viajes desde el Loop hasta O'Hare es igual los sábados lluviosos.  
- **Hipótesis Alternativa (H₁):** La duración promedio de los viajes desde el Loop hasta O'Hare es diferente los sábados lluviosos.  

---

## 🛠️ Herramientas utilizadas  

- **Lenguajes:** SQL, Python  
- **Librerías principales:**  
  - `pandas` — manipulación y análisis de datos  
  - `matplotlib.pyplot` — visualización de datos  
  - `requests` & `BeautifulSoup (bs4)` — extracción de información meteorológica  

---

## ✅ Conclusiones
