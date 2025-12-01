# 🔬 Laboratorio: Exploración de Azure Storage

**Logrado y documentado por:** *Tiffany Jordán* 

En este laboratorio exploré los fundamentos de Azure Storage, comprendiendo su propósito dentro de las soluciones de almacenamiento en la nube y la variedad de servicios que ofrece para manejar datos de forma flexible y segura como Blob Storage, Data Lake Storage Gen2, 
Azure Files y Azure Tables. Esta práctica me permitió familiarizarme con el entorno de Azure y preparar el contexto necesario para trabajar posteriormente con cada uno de sus servicios de almacenamiento. El laboratorio tuvo una duración aproximada de 15 minutos.

---

## Aprovisionar una cuenta de Azure Storage

1. Inicié sesión en el portal de Azure.
   
<img width="700" height="400" alt="Inicio de Sesión" src="https://github.com/user-attachments/assets/e78b5ae9-f5e3-4cb9-ba6c-face1122453a" />

2. Seleccioné **+ Crear un recurso** y elegí *Storage account*.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/c361f566-8ad2-4fe6-992e-0dc277552133" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ace8ad39-8870-4f9f-a1ea-4e36da2dc9a9" />

3. Configuré la cuenta con:
   - **Suscripción:** Seleccioné mi Suscripción de Azure.
   - **Grupo de Recursos:** Creé un nuevo grupo de recursos.
   - **Nombre de la Cuenta de Almacenamiento:** Un nombre único en minúsculas.
   - **Región:** Por defecto
   - **Rendimiento:** Estándar.
   - **Redundancia:** LRS.

> Usé LRS porque es la opción más económica y suficiente para un laboratorio.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e3a10829-da79-4f2d-ae9c-afdab230bfa9" />

4. En la sección **Avanzado**, verifiqué que el espacio de nombres jerárquico estuviera deshabilitado. 

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/72096754-6a3e-44c1-bde6-08f78153a472" />

5. En **Protección de datos**, desmarqué las opciones de eliminación temporal.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/21bbf95c-8045-4ada-9ce8-104d97d50b5a" />

6. Finalmente, creé la cuenta y esperé la implementación.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b4ebf6bb-9990-4930-aea0-929f94b718af" />

---

## Explorar el almacenamiento de Blobs

> El almacenamiento de blobs permite guardar archivos no estructurados como JSON, imágenes o documentos.

1. Descargué el archivo **product1.json**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/a03caf0a-9404-4e69-8425-521dc40de3de" />

2. En la cuenta de almacenamiento, abrí la sección **Contenedores**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6fa52e08-3868-4363-a930-ef623aa8cb07" />

3. Creé un contenedor llamado **data** con acceso **Privado**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/94874cec-d8e6-440d-8796-973e7a6ed530" />

4. Usé **Explorador de Almacenamiento** para ingresar al **Contenedor de Blobs**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d07bdddb-bce0-4efc-8128-efa2f7c5b56b" />

5. Creé un directorio virtual llamado **products** dentro de **data**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/11176df0-d2eb-45f0-89b7-9d5bbfe2995b" />

6. Observé que la carpeta **products** no aparecía al regresar al nivel superior porque las carpetas en el almacenamiento de blobs son virtuales y solo existen como parte de la ruta de un archivo. Como la carpeta de productos no contenía archivos, ¡no existe!.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b35effc6-8e74-4cfc-aa47-78adc0f38368" />

7. Cargué **product1.json** dentro de una carpeta llamada **product_data**, la cual se especificó en **Avanzado**, en **Subir a la Carpeta**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6c9e7f92-63a0-4f49-bde5-be90bfca1659" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/bace5cd8-608e-4d4b-a56b-5e2ebc9df84e" />

8. Verifique que `product1.json` esté dentro de *product_data*.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6caa887c-3bab-426d-9cf6-9f6419aa9f46" />
   
10. Observe que las carpetas virtuales no se pueden renombrar ni configurar.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/453d83ed-7488-48f2-9fa6-994797a2e3c6" />

---

# Explorar Azure Data Lake Storage Gen2

> Habilitar el espacio de nombres jerárquico convirtió las carpetas virtuales en directorios reales, permitiéndome renombrarlas, aplicar permisos ACL y obtener un mejor rendimiento para escenarios de big data.

1. Descargué `product2.json` desde: https://aka.ms/product2.json  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6fb1d84e-2480-4d93-b0c1-dfc0b74e81b4" />

2. En la cuenta de almacenamiento, en **Configuración**, ingresé a **Actualización de Data Lake Gen2**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/9e425f82-56a7-4171-9461-6d552ec8527e" />

3. Completé los pasos para habilitar el espacio de nombres jerárquico.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/bcaffc05-3eb6-45e3-9602-f1162a607d76" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/60dd099e-d354-47f6-9c89-b04065de89e7" />


> La actualización conservó los datos existentes y mejoró la semántica de directorios.

4. Regresé al **Explorador de almacenamiento** → *Contenedores de Blob* → *data*.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/025cc3d3-cfeb-4048-8872-cd08f0b53151" />

5. Abrí la carpeta **product_data**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/dcc7358e-4aa1-42df-9cd5-d239b46ade5b" />

6. Cargué `product2.json`.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f966b9cb-4199-4a0a-a6e4-af50b5cea0e4" />

> Verifiqué que los blobs (archivos) existentes siguieran funcionando y que los nuevos ya aprovecharan las funciones jerárquicas.

7. Al abrir el menú **…** en la carpeta **product_data**, pude ver opciones para renombrarla y configurar permisos, lo cual no estaba disponible antes.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d8d714a4-f5a9-4a41-a22d-b152dd0b9285" />

---

# Explorar Archivos de Azure

> Azure Files me permitió crear un recurso compartido SMB/NFS, útil para migraciones y aplicaciones que requieren un sistema de archivos tradicional.

1. En la cuenta de almacenamiento, accedí a **Recursos compartidos de archivos**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/11e23774-c5e1-479b-89c7-49f64d001884" />

2. Creé un recurso compartido llamado **files**, con el nivel **Transacciones optimizadas**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/13da8883-0dce-45b0-8a1d-e4593e4bbc86" />

3. En **Copia de seguridad**, desactivé la opción. Finalmente, creé el archivo.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2c7d73b4-fa9d-410d-bdc9-69aa7af7f705" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f9ffeabc-294a-4fed-8796-0a2f6d43a000" />

> Lo del Backup, redujo los costos durante el laboratorio; en un entorno productivo normalmente se habilitaría.

4. Abrí el recurso compartido **files**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/777f9da8-4834-4895-b376-61b6c6d0ecc1" />

5. Seleccioné **Conectar** y revisé los scripts generados para Windows, Linux y macOS.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/c6d164cb-1e22-4ec5-bcad-8ed54e9765c7" />

---

# Explorar Tablas de Azure

> Azure Tables me permitió trabajar con un almacén NoSQL flexible basado en clave-valor, ideal para datos semiestructurados.

1. En la sección **Tablas** dentro **Almacenamiento de Datos**, creé una tabla llamada **products**.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ad84157e-4f8d-49ca-a8d8-9c7ec64a5e05" />

2. Abrí el **Explorador de almacenamiento** → *Tablas* → *products*.  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/5f9209b9-acf3-4fb3-8f61-b3dbc2b90a5c" />

3. Seleccioné **+ Agregar entidad** e ingresé:
   - PartitionKey: 1  
   - RowKey: 1  
   - Nombre: Widget  
   - Precio: 2.99

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/c0b23a3f-9e54-4746-ad4c-22c8dcdea9f7" />

> PartitionKey definió la distribución y RowKey identificó de manera única la entidad dentro de la partición.

4. Agregué una segunda entidad con:
   - PartitionKey: 1  
   - RowKey: 2  
   - Nombre: Kniknak  
   - Precio: 1.99  
   - Discontinuado: true

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b09b53af-b0ea-4456-bbf6-579229e0d885" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b9671f8f-81b2-4650-a5b2-ea3ee937e214" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/471d71e8-53c6-4fd0-9113-eaf8826a7974" />

.
> Observé que pude agregar nuevas propiedades sin necesidad de migrar el esquema, gracias al modelo flexible de Azure Tables.

---

# Cierre del laboratorio
Una vez finalizado el laboratorio, eliminé el grupo de recursos que había creado para evitar cargos adicionales. Durante este proceso aprendí 
a trabajar con los distintos servicios de almacenamiento de Azure, comprendiendo sus características y casos de uso. En Azure Data Lake Storage 
Gen2 habilité el espacio de nombres jerárquico y entendí cómo mejora la administración de datos y directorios para cargas de trabajo analíticas 
y de big data. En Azure Files exploré cómo funcionan los recursos compartidos SMB/NFS y cómo pueden integrarse en entornos híbridos o migraciones 
desde sistemas locales. Además, en Azure Tables trabajé con un modelo NoSQL de tipo clave-valor, aprendiendo a crear y gestionar entidades sin 
necesidad de un esquema rígido. En conjunto, este laboratorio me permitió fortalecer mis habilidades en gestión de almacenamiento en la nube y 
comprender cuándo utilizar cada servicio según el tipo de información.
