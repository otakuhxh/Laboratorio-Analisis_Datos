# 🚀 Laboratorio: Aprovisionamiento y Consultas en Azure SQL Database 
**Logrado y documentado por:** *Tiffany Jordán* 

En este laboratorio aprovisioné una base de datos SQL en Azure y ejecuté consultas 
utilizando la base de datos de ejemplo **AdventureWorks**. Realicé cada paso 
manualmente desde el portal y añadí capturas para evidenciar el proceso. Esta práctica requirió una
suscripción de Azure con permisos administrativos.

## 1. Crear recurso Azure SQL
Ingresé al **Azure Portal**, seleccioné **+ Crear recurso**, busqué **Azure SQL** y elegí **Crear**.

📸 *Captura del portal seleccionando Azure SQL:*  

<img width="700" height="400" alt="Crear un Recurso" src="https://github.com/user-attachments/assets/62833b73-73e4-44b6-b571-756f60225bf6" />

<img width="700" height="400" alt="Búsqueda de Azure SQL" src="https://github.com/user-attachments/assets/b6f88d8b-b74c-4e9a-877d-c6c43a1ef80b" />

<img width="700" height="400" alt="Seleccionar Crear el Azure SQL" src="https://github.com/user-attachments/assets/46c1380e-e66d-48c2-963d-f8b6a1fe68a8" />

---

## 2. Seleccionar “Crear SQL Database”
Desplegue las opciones de **Azure SQL Database**, seleccionando **SQL database** y dando clic en **Crear**.

📸 *Captura de esta selección:*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b9992adf-9971-45f8-838f-41ec05bd6b2b" />

---

## 3. Configuración inicial de la base de datos
Ingresé los siguientes datos en la sección **Básico**:

- **Grupo de recursos:** RG1  
- **Nombre de la base:** AdventureWorks
- **Servidor:** Se dió clic en crear nuevo servidor y se ubicaron los datos:
    - **Servidor:** sql57178473
    - **Localización:** Por defecto.
    - **Autenticación:** SQL Authentication  
    - **Usuario administrador:** *(tu usuario)*  
    - **Contraseña:** *(tu contraseña)*
    - **Repetir Contraseña:** *(tu contraseña)*
      
- **¿Quieres usar SQL elastic Pool?:** No
- **Entorno de Carga de Trabajo:** Desarrollo
- **Computación + Almacenamiento:** Se dejó sin Cambios.
- **Redundancia de Almacenaminto de Respaldo:** Almacenamiento de Respaldo con Redundacia Local
>Se elegió Desarrollo y ese tipo de Redundancia de Almacenamiento dado que son la opción más económica y adecuada para una Base de Datos de Práctica Temporal.

📸 *Captura de esta configuración:*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/7a1d7815-c9f8-414f-9ed7-22c33ae64ccc" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/7f83aecb-068a-4e94-bd27-19ac259cedc3" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/54f2755a-4fbc-49bf-8151-0d045995c143" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/fa209567-02c0-4f9f-b0d2-3ec85db448b1" />


Luego, me dirigí a la sección de **Red**, donde apliqué la configuración:
- **Método de Conexión:** Punto de Conexión Público.
- **Reglas de Firewall:** En ambos, se selecciona Sí.

📸 *Captura de esta configuración:* 

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/3f4c8299-ff62-4df3-84a2-9c4bcf57d93f" />

En la sección de **Seguridad**, en **Habilitar Microsoft Defender para SQL** seleccioné **No ahora**.

📸 *Captura de esta configuración:* 

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1aceb6ee-9e8a-4d2b-bb17-fe17fc4c1190" />

En **Configuración Adicional**, en **Usar Data Existente** ubiqué **Sample**.

📸 *Captura de esta configuración:* 

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/c277684a-6c34-4308-974c-184577240b08" />

Finalmente, en **Revisar +Crear**, revisé que todo estuviera bien, y di clic en **Crear**.

📸 *Captura de esta configuración:* 

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/82eb6d80-4865-456f-a0fe-ad49c6995a92" />

---

## 4. Exploración y consultas SQL

Una vez completada la implementación, en **Notificaciones**, di clic en **Ir al Recurso** y abrí **Query Editor (Preview)** e inicié sesión con mi usuario SQL.

📸 *Captura de Notificaciones y el Recurso Creado :*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/7e891326-a4b6-44df-9f54-290802b90f13" />

📸 *Captura del Query Editor y Logueo:*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6271c2de-9fe4-4103-8300-7ed4595a5742" />

### 4.1. Visualizar la estructura

Exploré la carpeta **Tables** para ver todas las tablas disponibles.

📸 *Captura del listado de tablas:*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/dee68df4-feb8-4633-a804-e59e6b3e9bbb" />

### 4.2. Consultas a la Tablas
Para explorar las tablas y probar el entorno, ejecute las siguientes consultas:

**Primera Consulta (Toda la Tabla)**
>SELECT * FROM SalesLT.Product;

📸 *Captura de Ejecución - Consulta 1*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/dee68df4-feb8-4633-a804-e59e6b3e9bbb" />

**Segunda Consulta (Columnas Especíificas)**
>SELECT ProductID, Name, ListPrice, ProductCategoryID
>FROM SalesLT.Product;

📸 *Captura de Ejecución - Consulta 2*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/5f7edc06-545f-4a74-83b1-bcf7b3c15364" />

**Tercera Consulta (Inner Join)**
>SELECT 
>    p.ProductID, 
>    p.Name AS ProductName,
>    c.Name AS Category,
>    p.ListPrice
>FROM SalesLT.Product AS p
>INNER JOIN SalesLT.ProductCategory AS c
>    ON p.ProductCategoryID = c.ProductCategoryID;

📸 *Captura de Ejecución - Consulta 3*  

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0a4169a0-e92b-4406-aa16-d3e633bdc1f6" />

--- 
## 5. Cierre del Laboratorio y Resultados Obtenidos
Al finalizar el laboratorio realicé la limpieza del entorno para evitar costos innecesarios, eliminando el grupo de recursos RG1 por completo. Durante esta práctica aprendí a crear y aprovisionar una base de datos SQL en Azure, explorar tablas de ejemplo de AdventureWorks, ejecutar consultas SQL básicas y realizar un JOIN para relacionar información entre tablas. También configuré correctamente la conectividad, la autenticación y las reglas de firewall, asegurando el acceso seguro al editor de consultas.
