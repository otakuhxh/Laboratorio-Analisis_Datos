# 🧫 Explora el análisis en tiempo real en Microsoft Fabric

**Logrado y documentado por:** *Tiffany Jordán* 

En este laboratorio se exploró el análisis de datos en tiempo real 
con Microsoft Fabric. Se trabajó en la creación de un espacio de 
trabajo, la configuración de flujos de eventos para ingerir datos
de taxis y su almacenamiento en una casa de eventos mediante 
tablas KQL, también se planteó consultar y visualizar tendencias 
para comprender cómo Fabric facilita el análisis de datos en 
tiempo real. El laboratorio tomó aproximadamente 30 minutos y 
requirió un inquilino de Microsoft Fabric con permisos para 
crear espacios de trabajo y flujos de eventos.

---

## 1. Crear un espacio de trabajo

Antes de trabajar con datos en Fabric, creé un espacio de trabajo con la capacidad de Fabric habilitada.

> Se utilizó una capacidad que incluía Fabric (Trial, Premium o Fabric) para garantizar el funcionamiento de los motores necesarios.

1. Navegué y me logueé [https://app.fabric.microsoft.com/home?experience=fabric](https://app.fabric.microsoft.com/home?experience=fabric)

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/a5d446a9-0c6a-4e83-844c-df4b081d9341" />

2. En el menú izquierdo, seleccioné **Espacios de trabajo**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2f92c2f1-1a71-4493-8872-11116301331c" />

3. Creé un nuevo espacio de trabajo y seleccioné una licencia con capacidad de **Fabric** (Trial, Premium o Fabric), en **Avanzado**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/04c872ae-50de-4c44-9584-88b1dcf65bff" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/508e6b31-481d-419d-b8f1-6073855336bd" />

5. El espacio de trabajo apareció vacío.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e3cb1dd2-5a2b-44a1-af39-69330c3dbd1e" />

---

## 2. Crear un flujo de eventos

Conecté una fuente de datos en tiempo real mediante el **Centro en Tiempo Real**.

> El Hub en Tiempo Real centraliza fuentes de streaming y el *flujo de eventos* conecta fuentes y destinos, permitiendo aplicar transformaciones.

1. En el menú izquierdo, di clic en los **3 puntos (...)** y seleccioné **Centro en tiempo real**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/9f2780fb-f893-4066-8d32-f65a3c1e9c7a" />

2. En *Conectar a*, seleccioné **Fuentes de datos**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/efafdb4b-05c6-45c2-a206-bcba9b44fceb" />

3. Busqué **Taxi amarillo (Yellow Taxi sample)**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/31af9e65-a8c8-4297-8900-691b6c35cc49" />

4. Seleccioné **Conectar**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f326180f-211d-4f09-bb86-ca34db269ec8" />

5. Nombré la fuente como `taxi` y el flujo de eventos como `taxi-data`.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b5c57129-4c43-46bf-b540-6ef3fd0f50f7" />

6. Seleccioné **Siguiente**, luego **Conectar** y esperé su creación.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1ae41558-dd34-40e4-85b5-6ca29440cd19" />

7. Abrí el **flujo de eventos** para ver el lienzo con la fuente y la transmisión.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d91ea352-ead1-4ffb-a3fa-f9b168af337f" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/edde4451-9189-4dfe-8030-fc87e6d53a75" />

---

## 3. Crear una Eventhouse

El flujo ingirió los datos, pero aún no los almacenaba. Por lo que, creé una **Eventhouse**.

<p></p>

> Eventhouse incluye una base de datos **KQL**, ideal para consultar grandes volúmenes de datos en tiempo real.

1. En el menú izquierdo, seleccioné **Crear → Eventhouse**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d2656970-b109-48a1-9311-983bbc124f3f" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/af061f5d-3cf6-4d6e-b7d5-85c5abc493d6" />

2. Asigné un nombre único.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/32c2059b-ab57-4628-ba50-8a39a4432d16" />

3. Cerré los consejos emergentes.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/3a8dce2e-302d-4dab-96d5-22bd7be03dd0" />

4. Identifiqué la base de datos KQL generada automáticamente.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f2fe3f8a-fc10-4b4d-9227-745376e8c278" />

5. Seleccioné la base de datos y revisé el **conjunto de consultas** incluido, que contenía ejemplos de consultas KQL. Además, visualicé que no había tablas creadas.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f8033c46-e4af-43db-8c17-cbc9ff866403" />

## 4. Crear una tabla conectada al flujo

1. En la base de datos KQL, seleccioné **Obtener datos**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2f0fd29a-bc49-4fb1-bb10-b85a0cbaf1e8" />

2. Fuente: **Eventstream → Eventstream existente**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b110906d-7319-48dd-9e39-9024b8b0daa4" />

3. Creé una tabla nueva llamada **taxi**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1b85d589-2468-49c1-a56e-cfdbdadf00b1" />

4. Seleccioné el flujo de eventos `taxi-data`.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f1a61d0d-6de5-4ac7-947f-833dc5147050" />

5. Nombré la conexión como **taxi-table**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/18cb53dd-4135-4f7e-b1fe-e9708d6ff935" />

6. Completé los pasos y cerré la configuración.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1acb4932-4cd2-4a4c-af0c-e4f6af8edad1" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/cb18ce1b-43b1-4a99-868d-cd56bff00625" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d18816eb-2798-4920-8617-487e43a45adc" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/51bbf775-d071-4a05-960a-65a71ab55133" />

La tabla quedó conectada al flujo.

---

## 5. Verificar el flujo de eventos

1. Regresé al **Centro en tiempo real**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e4077909-4bff-4956-87b0-d3e32c6285cc" />

2. Abrí **Mis flujos de datos**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/c7fe5c02-f787-448f-b27e-cffddb583915" />

3. En `taxi-data`, seleccioné **… → Abrir flujo de eventos**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/9e132304-a0db-4f43-9a73-b51b4468bc4c" />

4. Verifiqué que aparecía el destino conectado. En caso de que no, seleccione **Actualizar**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6fe4b2cb-1a58-4b08-a90c-25b483bd5ed2" />

---

## 6. Consultar los datos capturados

Utilicé **KQL** para consultar la tabla en tiempo real.

1. Seleccioné la base de datos KQL.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/371034e7-5240-47f3-a6b6-6ed7a77048a3" />

2. Abrí el **conjunto de consultas**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/19f671d1-81dc-43b8-9a39-e79bc1601558" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/66c0b2c6-57ed-4de2-953d-941a28c8ec16" />

3. Ejecuté esta consulta para obtener una muestra rápida (100 filas):

```kql
taxi
| take 100
```
<p></p>

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1c36e301-2633-4b7b-a7c6-9436e918a9ad" />

### 6.1 Agrupar datos por hora

Para agrupar las recogidas de taxis por hora y ver tendencias, utilicé la siguiente consulta KQL:

```kql
taxi
| summarize PickupCount = count() by bin(todatetime(tpep_pickup_datetime), 1h)
```

<p></p>

* Ejecuté la consulta y observé los resultados por intervalos de 1 hora.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/4904191d-4f23-4ea1-a5dc-9cdfd04501d5" />

* Esperé unos segundos y volví a ejecutar; los valores cambiaban a medida que llegaban nuevos eventos.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/08185058-4aca-45a2-a3af-9b84a5bef15a" />

<p></p>

> `bin(..., 1h)` agrupa los eventos en bloques de una hora, facilitando detectar patrones y tendencias temporales.

---

## 7. Limpiar recursos

Al finalizar, eliminé el espacio de trabajo para evitar cargos continuos. Esto eliminó todos los recursos creados (Eventhouse, flujo de eventos y tablas).

Pasos realizados:

1. Seleccioné el icono de mi espacio de trabajo.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2997d3a7-cec5-495e-959b-425567389a78" />

2. Abrí **Configuración del espacio de trabajo**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/cfe11003-486b-4811-b2da-12a4cb710643" />

3. En la sección **General**, seleccioné **Eliminar este espacio de trabajo**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2b7252f4-a648-49db-b158-6f0585b8dc01" />

4. Confirmé la eliminación según las indicaciones.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/5e2985c2-d72e-443a-acf9-e0e8f1ce7099" />

---

## Fin del laboratorio

En este laboratorio aprovisioné un espacio de trabajo con capacidad de Fabric, donde se centralizaron todos los recursos necesarios 
para el análisis en tiempo real. Configuré flujos de eventos para ingerir datos de taxis en tiempo real, asegurando que la información 
fluyera correctamente desde la fuente de datos hasta el sistema. Posteriormente, almacené los datos en un Eventhouse mediante tablas KQL, 
lo que permitió mantener un registro estructurado y consultable de los eventos. Realicé consultas para explorar y analizar la información 
capturada, incluyendo la visualización de tendencias, como la cantidad de recogidas de taxis por hora, y validé que los datos se actualizaran 
conforme llegaban nuevos eventos. Esta experiencia me permitió comprender de manera práctica cómo Microsoft Fabric facilita la ingestión, el 
almacenamiento, la consulta y el análisis de datos en tiempo real, ofreciendo herramientas centralizadas y eficientes para gestionar información 
dinámica y en constante actualización.
