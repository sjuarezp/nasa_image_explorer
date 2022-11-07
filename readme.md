
# NASA Explorer

Proyecto demo para el Hackathon TECSUP 2022



## Pre-Requisitos

- Tener una cuenta creada en App-Gyver 
    - Public (https://www.appgyver.com/)
    - BTP (https://developers.sap.com/tutorials/appgyver-subscribe-service.html)   


## Recursos 

- NASA Open API
    - URL API: https://api.nasa.gov/
    - Documentación: https://images.nasa.gov/docs/images.nasa.gov_api_docs.pdf
    








## Paso 1: Crear Applicación


Creamos nuestra aplicación:
![SJP APP](/demo/docs/assets/image1.png)



## Paso 2: Titulo de la aplicación
Seleccionamos el título:
![SJP APP](/demo/docs/assets/image2.png)


Escribimos:
```
 NASA Image Explorer
```
![SJP APP](/demo/docs/assets/image3.png)


Seleccionamos el texto debajo del título y escribimos :
```
Busca imágenes que tiene la NASA sobre algún tema de interés
```

![SJP APP](/demo/docs/assets/image4.png)

Arrastramos y soltamos el control "Input Field" debajo del texto y escribimos los siguientes datos:

Clave | Valor
---|---
 Label:| `¿Qué deseas buscar?`
 Placeholder Text:| `Escribe aquí`
 

![SJP APP](/demo/docs/assets/image5.png)


## Paso 3: Creación de Variables de applicación

Realizamos la creación de las variables de la aplicación:
![SJP APP](/demo/docs/assets/image6.png)

Click en `ADD APP VARIABLE` y creamos 4 variables de Aplicación:  
![SJP APP](/demo/docs/assets/image7.png)

Creamos las siguientes 4 variables

Clave | Valor
---|---
 Variable Name:| `original_image_url`
 Variable Value:| `Image URL`

 Clave | Valor
---|---
 Variable Name:| `resultado_titulo`
 Variable Value:| `text`

 Clave | Valor
---|---
 Variable Name:| `resultado_url`
 Variable Value:| `text`

 Clave | Valor
---|---
 Variable Name:| `search_query`
 Variable Value:| `text`
 

 Debería quedar de la siguiente manera:
![SJP APP](/demo/docs/assets/image8.png)

Regresamos al modo de Edición
![SJP APP](/demo/docs/assets/image9.png)

## Paso 4: Completar interfaz gráfica:

Arrastramos y solamos un control de tipo `Button` y escribimos `Buscar`:
![SJP APP](/demo/docs/assets/image10.png)

Arrastramos un control de tipo `Title` 
![SJP APP](/demo/docs/assets/image11.png)
escribimos el texto: `Resultados:`
![SJP APP](/demo/docs/assets/image12.png)


Arrastramos y soltamos un control de tipo `Large image list item`:
![SJP APP](/demo/docs/assets/image14.png)

Debería quedar de la siguiente manera:
![SJP APP](/demo/docs/assets/image15.png)



## Paso 5: Consulta API REST NASA:
Click en el menú `DATA`
![SJP APP](/demo/docs/assets/image16.png)

Click en `ADD DATA RESOURCE`
![SJP APP](/demo/docs/assets/image17.png)

Click en `REST API direct integration`
![SJP APP](/demo/docs/assets/image18.png)


Click en `BASE` y completar los campos con la siguiente info:
 
 Clave | Valor
---|---
 Resource ID:| `busqueda_nasa`
 Short description:| `Servicio de Busqueda de imagenes en API NASA`
 Resource URL:| `https://images-api.nasa.gov`

![SJP APP](/demo/docs/assets/image18.5.png)


Click en `GET COLLECTION (GET)` y completas con la siguiente infirmación:

Clave | Valor
---|---
 Relative path:| `/search?q={query}`
 Response key path:| `collection.items`

![SJP APP](/demo/docs/assets/image19.png)

Click en `+` de `URL Placeholder`
![SJP APP](/demo/docs/assets/image20.png)

Generará el siguiente registro con valores por default:
![SJP APP](/demo/docs/assets/image22.png)

Modificar los valores por default considerando los siguientes:

Clave | Valor
---|---
 Label:| `query`
 Key:| `query`
 Value type:| `text`
 Is encode:| `true`
 Is static:| `false`
Is Optional:| `false`

![SJP APP](/demo/docs/assets/image23.png)

Click en la pestaña `TEST` para 
![SJP APP](/demo/docs/assets/image24.png)


Completar el texto con `nazca` para probar la llamada al servicio
![SJP APP](/demo/docs/assets/image26.png)

Click en el botón `RUN TEST` para probar la ejecución del servicio:
![SJP APP](/demo/docs/assets/image27.png)

Click en `SET SCHEMA FROM RESPONSE` para guardar la estructura respondida por el servicio
![SJP APP](/demo/docs/assets/image28.png)

En la pestaña `SCHEMA` nos deberái mostrar la estructura de respuesta de la siguiente manera:
![SJP APP](/demo/docs/assets/image29.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image30.png)

Click en `IU CANVAS` para regresar al modo edición:
![SJP APP](/demo/docs/assets/image31.png)

Click en el `Input field` para seleccionarlo:
![SJP APP](/demo/docs/assets/image33.png)


Click en `Value` para mapear el valor escrito en el input:
![SJP APP](/demo/docs/assets/image34.png)

Click en `Data and Variables`
![SJP APP](/demo/docs/assets/image35.png)

Click en `App variable`
![SJP APP](/demo/docs/assets/image36.png)

Seleccionamos `search_query`
![SJP APP](/demo/docs/assets/image37.png)

Click en `SAVE`
![SJP APP](/demo/docs/assets/image38.png)


## Paso 6: Configuración de la llamada al API:

Seleccionamos el botón de búsqueda:
![SJP APP](/demo/docs/assets/image40.png)

Click en `Add logic to BUTTON1`:
![SJP APP](/demo/docs/assets/image41.png)

Arrastrar y soltar la lógica `Get record collection`:
![SJP APP](/demo/docs/assets/image42.png)

Enlazar el evento `Compenent tap` a la lóogica `Get record collection`:
![SJP APP](/demo/docs/assets/image44.png)

Seleccionamos `Get record collection`:
![SJP APP](/demo/docs/assets/image45.png)

Click en `busqueda_nasa`:
![SJP APP](/demo/docs/assets/image46.png)

Click en `Save`
![SJP APP](/demo/docs/assets/image47.png)

Click en `query` tal como muestra la imágen:
![SJP APP](/demo/docs/assets/image48.png)

Click en el tile: `Data and Variables`
![SJP APP](/demo/docs/assets/image50.png)

Click en el tile `App variable`:
![SJP APP](/demo/docs/assets/image51.png)

Seleccionamos la variable: `search_query`:
![SJP APP](/demo/docs/assets/image52.png)

Click en el botón `SAVE`:
![SJP APP](/demo/docs/assets/image53.png)

Click en `Variables`
![SJP APP](/demo/docs/assets/image54.png)



Click en `DATA VARIABLES`:
![SJP APP](/demo/docs/assets/image56.png)

Click en `ADD DATA VARIABLE`:
![SJP APP](/demo/docs/assets/image57.png)

Click en `busqueda_nasa`:
![SJP APP](/demo/docs/assets/image58.png)

Debería quedar creada la variable de la siguiente manera:
![SJP APP](/demo/docs/assets/image59.png)

Regresamos al modo edición:
![SJP APP](/demo/docs/assets/image60.png)


Seleccionamos el botón `Buscar`:
![SJP APP](/demo/docs/assets/image62.png)

Abrimos el panel de lógica del botón:
![SJP APP](/demo/docs/assets/image63.png)

Arrastramos la lógica `Set data variable` al panel de edición:
![SJP APP](/demo/docs/assets/image64.png)

Debería queda de la siguiente manera:
![SJP APP](/demo/docs/assets/image65.png)

Conectamos la salida superior del control `Get record collection` a la lógica `Set data variable`:
![SJP APP](/demo/docs/assets/image66.png)

Seleccionamos la lógica `Set data variable`:
![SJP APP](/demo/docs/assets/image67.png)

Damos click en `Data variable name` según la imagen:
![SJP APP](/demo/docs/assets/image68.png)

Click en el tile: `Data variable`:
![SJP APP](/demo/docs/assets/image69.png)

Seleccionar `busqueda_nasa1`:
![SJP APP](/demo/docs/assets/image70.png)


Guardamos los cambios:
![SJP APP](/demo/docs/assets/image71.png)

Click en `Record collection` según la imagen:
![SJP APP](/demo/docs/assets/image72.png)

Click en el tile: `Output value of another node`: 
![SJP APP](/demo/docs/assets/image73.png)

Seleccionar `Get record collection`:
![SJP APP](/demo/docs/assets/image74.png)

Seleccionar la opción: `Get record collection/Collection of records` y guardar cambios:
![SJP APP](/demo/docs/assets/image75.png)

Seleccionar el control de galería:
![SJP APP](/demo/docs/assets/image77.png)

Click en `Repeat with`:
![SJP APP](/demo/docs/assets/image78.png)


Click en `Data and Variables`:
![SJP APP](/demo/docs/assets/image80.png)

Seleccionar `Data variable`:
![SJP APP](/demo/docs/assets/image81.png)

Seleccionamos `busqueda_nasas1`:
![SJP APP](/demo/docs/assets/image82.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image83.png)

Seleccionamos el primer item de la lista y damos click en `Image source` según la imagen:
![SJP APP](/demo/docs/assets/image85.png)

Seleccionamos el tile `Formula`:
![SJP APP](/demo/docs/assets/image86.png)

Damos click a la fórmula:
![SJP APP](/demo/docs/assets/image87.png)


Click en `Currently repeated data items`:
![SJP APP](/demo/docs/assets/image88.png)

Seleccionamos la opción: `repeated.current.links` y damos docle click:
![SJP APP](/demo/docs/assets/image89.png)


La fórmula debería qeudar de la siguiente manera:
![SJP APP](/demo/docs/assets/image90.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image91.png)

Guardamos cambios de la fórmula:
![SJP APP](/demo/docs/assets/image92.png)

Click en `Title label`:
![SJP APP](/demo/docs/assets/image93.png)

Click en el tile: `Formula`:
![SJP APP](/demo/docs/assets/image94.png)

Seleccionamos la fórmula:
![SJP APP](/demo/docs/assets/image95.png)

Eliminamos el texto actual:
![SJP APP](/demo/docs/assets/image96.png)


Click en `Currently repeated data items`:
![SJP APP](/demo/docs/assets/image97.png)

Seleccionamos  `repeated.current.data[0].title`:
![SJP APP](/demo/docs/assets/image98.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image99.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image100.png)

Click en `Description test`:
![SJP APP](/demo/docs/assets/image101.png)

Seleccionamos el tile `Formula`:
![SJP APP](/demo/docs/assets/image102.png)

Seleccionamos el campo `Formula`:
![SJP APP](/demo/docs/assets/image103.png)

Eliminamos el contenido actual:
![SJP APP](/demo/docs/assets/image104.png)

Seleccionamos `Currently repeated data items` y luego seleccionar: `repeated.current.data[0].description`:
![SJP APP](/demo/docs/assets/image105.png)

La fórmula debería quedar de la siguiente manera:
![SJP APP](/demo/docs/assets/image106.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image107.png)

Guardamos cambios:
![SJP APP](/demo/docs/assets/image108.png)

Guardamos cambios para todo el proyecto:
![SJP APP](/demo/docs/assets/image109.png)


Finalmente vamos al menu `LAUNCH`
![SJP APP](/demo/docs/assets/image110.png)


Click en `OPEN APP PREVIW PORTAL`:
![SJP APP](/demo/docs/assets/image111.png)



Visualización en  `APP PREVIEW PORTAL`:
![SJP APP](/demo/docs/assets/image112.png)




Visualización en  `APP PREVIEW MOBILE`:
![SJP APP](/demo/docs/assets/image113.png)


