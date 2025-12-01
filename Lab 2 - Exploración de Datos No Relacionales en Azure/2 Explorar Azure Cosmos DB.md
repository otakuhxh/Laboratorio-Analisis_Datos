# ⭐ Exploración de Azure Cosmos DB
**Logrado y documentado por:** *Tiffany Jordán* 

En este laboratorio aprovisioné una cuenta de Azure Cosmos DB, creé una base de datos y un contenedor 
de ejemplo, agregué y visualicé elementos JSON, y ejecuté consultas tipo SQL desde Azure Portal para 
recuperar información. A través de este proceso comprendí cómo Cosmos DB permite almacenar y consultar 
datos no relacionales de manera flexible y distribuida. El laboratorio tomó aproximadamente 15 minutos y 
requiere una suscripción de Azure con permisos administrativos.

## Crear una cuenta de Cosmos DB

Para usar Cosmos DB, aprovisioné una cuenta de Cosmos DB en mi
suscripción de Azure, para ello:

1.  Iniciar Sesión en el **Portal de Azure**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0ce0de8d-47df-4dcd-be9e-83c981eb7ae4" />

2.  En Azure Portal seleccioné **+ Crear un recurso** y busqué **Azure
    Cosmos DB**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/41daf387-7632-42c2-af29-168ee767b618" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2a6a53ee-96e2-4080-9893-136a9f851a00" />

3.  En los resultados, seleccioné *Azure Cosmos DB* y luego **Crear**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/231ac29d-d0be-4fd9-a0b4-c32b11970d53" />

4.  En el mosaico de *Azure Cosmos DB para NoSQL*, seleccioné **Crear**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6ff82b4a-9c91-4d2b-a158-eb77f045d6a9" />

<p></p>

> Se eligió *Azure Cosmos DB para NoSQL* dado que permitió almacenar y consultar datos JSON con
> un lenguaje de consulta simple similar a SQL.

5. A continuación, ingresé los siguientes parámetros:

-   **Tipo de carga de trabajo:** Aprendizaje
-   **Suscripción:** La asignada a mi entorno
-   **Grupo de recursos:** Existente o uno nuevo
-   **Nombre de la cuenta:** Un nombre único
-   **Zonas de disponibilidad:** Deshabilitadas
-   **Ubicación:** Una región recomendada
-   **Modo de capacidad:** Rendimiento aprovisionado
-   **Nivel gratuito:** Aplicado si estaba disponible
-   **Limitar rendimiento total:** No seleccionado

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/beb7e4fb-078b-4138-b6e8-6f509c3454ae" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/06e6f38b-a99a-4777-93be-429c8dfa1045" />

<p></p>

> Estas configuraciones facilitaron el inicio, mantuvieron los costos
> bajos y aseguraron un rendimiento estable durante el laboratorio.

6. Una vez validada la configuración, seleccioné **Crear** y esperé a que
la cuenta se aprovisionara. Después, accedí al recurso implementado.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/555a7b9c-a14f-4829-9170-142d08cf267c" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/17e00a37-5797-47a6-b33f-0a0ea1a67890" />

---

## Crear una base de datos de muestra

1.  Abrí la cuenta de Cosmos DB.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/39e68338-cb30-4389-9f2d-9a52b9249c3f" />

2.  En el menú lateral, seleccioné **Explorador de datos**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/a5cdc41f-4c5a-4bc1-ad85-c30093f28a93" />

3.  Seleccioné **Iniciar inicio rápido** para generar una base de datos
    y contenedor de ejemplo.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2cbece70-fd09-4022-aeda-048c0cd21bcc" />

4.  Revisé la configuración predeterminada en *Nuevo contenedor* y
    seleccioné **Aceptar**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/019b2a1a-7e4d-45b2-86e6-d5f064bc5291" />

<p></p>

> El inicio rápido creó automáticamente la base de datos **SampleDB** y
> el contenedor **SampleContainer**, permitiéndome practicar sin
> necesidad de definir un esquema manualmente.

Esperé hasta que ambos recursos se crearan completamente.

---

## Ver y crear elementos

Dentro del Explorador de datos:

1.  Expandí **SampleDB → SampleContainer → Items**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/fccddf35-97b9-4184-8fe5-59ab11204e7f" />

2.  Visualicé los elementos existentes en formato JSON.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8c391c9d-c25c-4da7-884c-5bdd8107b765" />

3.  Seleccioné **Nuevo elemento** para crear un documento JSON en
    blanco.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6634bea0-5c72-471f-834b-390a0e21aa5b" />

4.  Reemplacé el contenido por:

``` JSON
{
   "name": "Road Helmet,45",
   "id": "123456789",
   "categoryID": "123456789",
   "SKU": "AB-1234-56",
   "description": "The product called "Road Helmet,45" ",
   "price": 48.74
}
```
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e4a0b05f-d0bd-4433-84a3-72f86c5fd1e7" />

5.  Seleccioné **Guardar**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/27108d3a-6f77-4816-b43b-12678fdf20df" />

<p></p>

> Cosmos DB agregó automáticamente propiedades del sistema como `_rid`,
> `_self`, `_etag`, `_ts` y `_attachments`, utilizadas internamente para
> control de concurrencia, indexación y administración.

---

## Consultar la base de datos

1.  Seleccioné **Nueva consulta SQL**.\

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2e725e85-7394-4a31-b082-4e4927a9b77a" />

2.  Ejecuté la consulta predeterminada:

``` sql
SELECT * FROM c
```

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/9400484f-7660-4188-9d4b-506c6ffe7ba6" />

3.  Observé la salida con todos los documentos en formato JSON.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2b9ed8bc-0e8c-45d3-b6dc-dd80bd108be2" />

4.  Modifiqué la consulta para filtrar por texto en el campo `name`:

``` sql
SELECT *
FROM c
WHERE CONTAINS(c.name,"Helmet")
```


<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6c686995-9668-4e8d-82e8-d783760e8614" />

5.  Ejecuté la consulta revisada.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/b6e835ea-5f58-4258-8234-8bf86e53d85d" />

<p></p>

> La API NoSQL permite usar un lenguaje de consultas similar a SQL para
> trabajar con documentos JSON sin necesidad de configuraciones
> adicionales.

Finalmente, cerré el editor descartando los cambios.

---

# Cierre del laboratorio

Una vez finalizado el laboratorio, eliminé el grupo de recursos que
había creado para evitar cargos adicionales. Este laboratorio me
permitió comprender cómo aprovisionar y administrar una cuenta de Azure
Cosmos DB, crear bases de datos y contenedores, trabajar con documentos
JSON, configurar consultas tipo SQL y manipular datos NoSQL desde el
Explorador de datos del portal. Gracias a esta experiencia práctica, reforcé conocimientos fundamentales sobre
bases de datos distribuidas, consultas flexibles y administración de
recursos en Azure, habilidades esenciales para trabajar con aplicaciones
modernas en la nube.
