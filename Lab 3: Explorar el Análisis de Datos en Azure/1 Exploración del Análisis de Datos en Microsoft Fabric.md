# ☁️ Exploración del análisis de datos en Microsoft Fabric

**Logrado y documentado por:** *Tiffany Jordán* 

En este laboratorio exploré el entorno de Microsoft Fabric Lakehouse, un espacio 
unificado diseñado para gestionar e interactuar con datos en la nube. 
La actividad introdujo los componentes principales del Lakehouse y 
su relación con la ingesta, el almacenamiento y el análisis de datos
, proporcionando una visión inicial del funcionamiento de esta 
plataforma dentro del ecosistema de Microsoft Fabric.

---

## Antecedentes del conjunto de datos NYC Taxi – Green

El conjunto de datos *NYC Taxi – Green* contiene información detallada sobre viajes 
de taxi en Nueva York, incluyendo horarios, ubicaciones, distancias, 
tarifas y número de pasajeros. Es un dataset ampliamente utilizado 
en el análisis urbano, predicción de demanda y detección de anomalías.  
En este laboratorio utilicé este conjunto de datos real para practicar procesos 
de ingesta y análisis en Microsoft Fabric. Este laboratorio duró 25 minutos, y se uitlizó 
una cuenta con Licencia de Microsoft Fabric

---

### 1. Crear un espacio de trabajo


> Un espacio de trabajo es el contenedor de todos los recursos del entorno Fabric.


Antes de comenzar a trabajar con datos, inicie sesión y creé un **espacio de trabajo** con Fabric habilitado.

Pasos realizados:

1. Ingresé a: https://app.fabric.microsoft.com/home?experience=fabric  
2. Seleccioné **Espacios de trabajo (🗇)**.  
3. Creé un espacio de trabajo nuevo,

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8cb27203-e382-41ba-9114-36d5cdc2c611" />

<p></p>

El espacio de trabajo se creó vacío, listo para usarse.

---

### 2. Crear un Lakehouse

Luego creé mi primer Lakehouse dentro del espacio de trabajo.

Pasos realizados:

1. Seleccioné los **3 puntos (...)**, en **Crear** → **Lakehouse**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/135da41c-13f9-4180-ad0e-4080fd341188" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6a53f8a3-a2b6-451a-a6d3-6be794680212" />

2. Le asigné un nombre único y di clic en **Crear** .  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/73f5e74f-64c6-471b-867e-bb3ecbec11f4" />

3. Esperé aproximadamente un minuto mientras se aprovisionaba.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b6c21a60-b966-4330-9374-21d3f770e4b3" />

El Lakehouse se creó con:

- Carpeta **Tablas** (para tablas Delta consultables con SQL).  
- Carpeta **Archivos** (para datos sin procesar en OneLake).

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d5252a12-9158-4673-a4ca-834b2b95bb09" />

---

### 3. Ingesta de datos mediante canalización

Para incorporar datos utilicé una canalización con una actividad **Copiar datos**.

Pasos realizados:

1. Desde el Lakehouse seleccioné **Obtener datos → Nueva canalización de datos**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b7886b0c-37fd-4da5-a447-af53760cc5d4" />

2. Creé la canalización *Ingerir datos*.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d0d4774c-80fb-4c87-b947-e6c2ba09c829" />

3. Seleccioné la fuente **Datos de muestra → NYC Taxi - Green**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f66cb402-c04b-4c5a-8b9b-52fdbeeefc39" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/3ec15574-47b0-459d-9e69-f35a527900dd" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2f9dc092-3d20-4e9d-a18c-bf7cf2c8d41b" />

4. Configuré el destino:  
   - **Carpeta raíz:** Tablas  
   - **Configuración de Carga:** Crear nueva tabla 
   - **Nombre:** `taxi_rides`  
   - **Habilitar Partición:** No Selecionado

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0c596ec0-d173-42f6-b8f1-bdea38d26470" />

5. Seleccioné **Siguiente** y elegí **Guardar + Ejecutar** para iniciar la ingesta.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6fa5a4b0-90b0-4336-8631-7767688d93cb" />

<p></p>

> La canalización comenzó a ejecutar la copia del dataset (más de 75 millones de filas).  

6. Desde el panel de **Salida** supervisé el progreso hasta su finalización.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/4d12a518-7c40-4fbb-a962-df6f96b555ce" />

7. Finalmente, actualicé el explorador de Lakehouse y confirmé que la tabla **taxi_rides** había sido creada.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/97778cda-d21e-4206-95fd-54df2a1bfb1a" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/bb74f52c-c5fb-4aad-a9c3-bf35853c18cb" />

---

### 4. Consultar datos con SQL

Con los datos ya cargados, ejecuté consultas SQL directamente desde el punto de análisis SQL del Lakehouse.

Pasos realizados:

1. Cambié la vista a **Punto de análisis SQL**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/486f2be1-78de-4829-88ff-03530c87f94e" />

2. Seleccioné **Nueva consulta SQL**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/afe7a9c6-d23a-43f5-a33e-c05c0d101425" />

3. Ejecuté la consulta:

```sql
SELECT  DATENAME(dw,lpepPickupDatetime) AS Day,
        AVG(tripDistance) AS AvgDistance
FROM taxi_rides
GROUP BY DATENAME(dw,lpepPickupDatetime)
```
<p></p>

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/190d917a-4259-411c-bf97-7824d3ec7724" />

# 5. Limpiar recursos

Una vez que terminé todas las actividades del laboratorio, procedí a eliminar el grupo de recursos que había creado, porque de esta forma, se eliminan todos los elementos creados en el laboratorio y ayuda a evitar cargos continuos.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/55bcb2a4-4e6f-468d-9348-75379e866c30" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/95d127b4-3fb5-4531-9eed-f28e1133aa64" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/474790c8-63ff-4829-9a05-a205ed7f8977" />

# Cierre del Laboratorio

Al finalizar este laboratorio pude recorrer el flujo completo de trabajo dentro de Microsoft Fabric para la ingesta y análisis de datos, desde la creación de un entorno aislado hasta la carga, consulta y exploración del conjunto de datos de taxis de Nueva York. Esta práctica me permitió entender cómo Fabric unifica herramientas clave dentro de un mismo espacio como Lakehouse, canalizaciones y consultas SQL, y cómo estos componentes facilitan el análisis de datos a gran escala. Con este recorrido obtuve una visión clara de cómo se gestionan, transforman y consultan datos reales en Fabric, además de reforzar la importancia de limpiar los recursos utilizados para evitar costos innecesarios.
