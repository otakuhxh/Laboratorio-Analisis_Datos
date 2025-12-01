# 📈 Exploración de visualización de datos con Power BI

**Logrado y documentado por:** *Tiffany Jordán*

En este laboratorio exploré los fundamentos de la visualización de datos con Power 
BI. Se trabajó en la importación y modelado de datos, la creación de relaciones y 
jerarquías, y la construcción de informes interactivos con tablas, gráficos y mapas. 
El laboratorio tomó aproximadamente 20 minutos y requirió la instalación de Power BI Desktop.

---

## 1. Instalación de Power BI Desktop

Descargué e instalé Power BI Desktop desde [este enlace](https://aka.ms/power-bi-desktop?azure-portal=true) usando el asistente de instalación. Esta herramienta me permitió crear modelos e informes localmente antes de compartirlos.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/541f762f-40b5-4d94-8b8c-57a4643cccf2" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/31c726ba-9739-410f-85be-31d7e73815c8" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/d9d3aad3-0b4c-41c2-b90d-ef0d66d3ce01" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/4792d203-44b9-4461-86d5-7d047299306e" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ee420126-7fcc-4690-b420-e5394c62ae92" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/36bf2029-5003-4800-a6fe-7be60553f2ac" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6c3feba5-d016-42eb-9393-1bcb9807162d" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/a68cf44a-9863-4655-b3ff-c13086ffc938" />

---

## 2. Importar datos

1. Abrí Power BI Desktop, y seleccioné **Informe en Blanco**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8a758213-f670-485f-b408-83a0cce3c615" />

2. En **Obtener datos → Web**, ingresé las siguientes URLs y cargué los datos:

   * Clientes: `https://github.com/MicrosoftLearning/DP-900T00A-Azure-Data-Fundamentals/raw/master/power-bi/customers.csv`

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0b893ef0-e67a-4593-a2e2-ea8c0ddae709" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/bd7a97a5-7ab1-4321-b75d-2e11e163972f" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6ceb3959-d78e-4497-a7e7-0efd1f1983c6" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/435bbee8-752a-456b-a888-096dc953082a" />

<p></p>

   * Productos: `https://github.com/MicrosoftLearning/DP-900T00A-Azure-Data-Fundamentals/raw/master/power-bi/products.csv`

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/3339ee04-d608-4ac9-a93c-b8659059e30e" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ea6b5c6f-3c04-475e-98e9-daefffa32762" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/74529e69-43f4-42e6-b07c-62342178d9b8" />

<p></p>

   * Pedidos: `https://github.com/MicrosoftLearning/DP-900T00A-Azure-Data-Fundamentals/raw/master/power-bi/orders.csv`

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ff56b9ff-fb07-49eb-b67d-9c89b287061a" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/79bc671e-e39c-4830-9279-920aac3803bc" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6b87a5d0-f819-4351-a944-0421e92b723d" />

---

## 3. Explorar y modelar datos

1. En la pestaña **Modelo**, organicé las tablas y oculté paneles innecesarios.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f14bad4d-324b-4336-87c8-b5c8c895c56b" />

2. En la tabla **Pedidos**, configuré `Ingresos` como **Moneda**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8f1456fc-8c32-45e3-8bb7-bbc3d39df862" />

3. Creé una jerarquía de **Categoría** y añadí a **NombreProducto**. A la jerarquía se le renombró como `Producto categorizado`.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/4587dd5d-713a-4b0d-a37f-12bde89b3084" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/cadeac38-27fb-448e-9456-a024495a09cf" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/5f4f224c-d82a-4a48-aadc-da7847e02b02" />

4. En la tabla **Clientes**, configuré la columna `Ciudad` como **Categoría de datos → Ciudad**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/348310fc-6979-4d4e-aeec-ac5215c8bd13" />

<p></p>

> **Consejo:** Formatear y categorizar campos facilita la lectura y análisis geográfico de los datos.

---

## 4. Crear un informe

1. Verifiqué que la opción de visualización de mapas estuviera activada en **Opciones → Seguridad → Usar imágenes de mapa y mapa relleno**.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/bb6bf318-476d-40e0-8868-3bbbca4765d6" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e31cb9f9-209b-4181-a8e2-e0fd90191092" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6ef8a9ad-35b2-4188-b967-d7389f981b8b" />

2. En la pestaña **Vista de informe**, agregué un cuadro de texto con el título "Informe de ventas".

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/2d32fd30-9ef4-4f82-a486-a78c1e46e8e9" />

3. Agregué la jerarquía `Producto categorizado` y la columna `Ingresos` para crear una tabla de productos categorizados con ingresos.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/925cbfd1-2840-41b4-8d4c-8b9a1b203f60" />

4. Convertí la tabla en un **gráfico de columnas apiladas** para mostrar ingresos por categoría, activé la función de exploración en profundidad para pasar de ver las **Categorías** a **Productos** y explorar.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/083ea17a-1ef6-4af1-bca2-46e9ed99bbd6" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ac605a08-6ac1-4db5-a565-344779679a9a" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/f19e30d6-e2ac-462f-8d45-12cbb87e64d1" />

5. Creé un **gráfico circular** con `Cantidad` por `Categoría` y un **mapa** con `Ciudad` e `Ingresos` para visualizar datos geográficamente.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/e9ac9686-af70-4c64-9a71-77804c05eac8" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/cab9a7c6-422b-45bd-ac79-85b4c79634ce" />

6. Interactué con los elementos visuales usando resaltado cruzado para analizar patrones por ciudad.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/6657583e-ab4a-4abd-b4d1-71a22114b1ff" />

---

## 5. Guardar y publicar

1. Guardé el archivo como `.pbix` para conservar modelo, consultas e informes.

<p></p>

> **Nota**: Publicar en Power BI Service permite la colaboración, actualización automática y exploración de datos en línea. Sin embargo, para usarlo se necesita una cuenta de paga o empresarial.

---

## Fin del laboratorio

En este laboratorio consolidé mis habilidades en la visualización de datos con Power BI, importando y modelando datos de clientes, productos y pedidos. Creé relaciones y jerarquías que permitieron un análisis más profundo, formateé y clasifiqué campos para mejorar la comprensión de la información, y construí informes interactivos con tablas, gráficos y mapas. Además, exploré los datos mediante funciones de exploración en profundidad y resaltado cruzado, lo que me permitió identificar patrones y relaciones relevantes. Esta práctica me permitió comprender cómo Power BI facilita transformar datos sin procesar en visualizaciones interactivas y útiles para la toma de decisiones empresariales.
