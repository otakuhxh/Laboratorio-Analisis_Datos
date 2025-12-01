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

La canalización comenzó a ejecutar la copia del dataset (más de 75 millones de filas).  
Desde el panel de **Salida** supervisé el progreso hasta su finalización.

Finalmente, actualicé el explorador de Lakehouse y confirmé que la tabla **taxi_rides** había sido creada.

---

### 4. Consultar datos con SQL

Con los datos ya cargados, ejecuté consultas SQL directamente desde el punto de análisis SQL del Lakehouse.

Pasos realizados:

1. Cambié la vista a **Punto de análisis SQL**.  
2. Seleccioné **Nueva consulta SQL**.  
3. Ejecuté la consulta:

```sql
SELECT  DATENAME(dw,lpepPickupDatetime) AS Day,
        AVG(tripDistance) AS AvgDistance
FROM taxi_rides
GROUP BY DATENAME(dw,lpepPickupDatetime)
```

# 5. Limpiar recursos

Una vez que terminé todas las actividades del laboratorio, procedí a eliminar el grupo de recursos que había creado para evitar cargos adicionales y mantener mi entorno de Azure ordenado.

# Cierre del Laboratorio

Una vez finalizado el laboratorio, eliminé el grupo de recursos que había creado para evitar cargos adicionales. Durante este ejercicio aprendí a aprovisionar y configurar una base de datos SQL en Azure desde cero, conectarme mediante Query Editor y ejecutar consultas sobre las tablas de ejemplo de AdventureWorks, lo que me permitió reforzar mi entendimiento del modelo relacional en un entorno en la nube. Además, comprendí mejor cómo se gestionan los recursos dentro de un grupo, el uso de herramientas de consulta integradas y la importancia de la limpieza del entorno para un uso eficiente y responsable de los servicios en la nube. Este laboratorio fortaleció mis habilidades para trabajar con bases de datos administradas y me preparó para futuros escenarios reales en proyectos empresariales.
