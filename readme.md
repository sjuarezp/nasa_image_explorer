
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
 label:| `¿Qué deseas buscar?`
 Placeholder Text:| `Escribe aquí`
 

![SJP APP](/demo/docs/assets/image5.png)


## Paso 3: Creación de Variables de applicación

Realizamos la creación de las variables de la aplicación:
![SJP APP](/demo/docs/assets/image6.png)

Click en "ADD APP VARIABLE" y creamos 4 variables de Aplicación:  `APP VARIABLE`
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
 

 
![SJP APP](/demo/docs/assets/image8.png)

Regresamos al modo de Edición
![SJP APP](/demo/docs/assets/image9.png)

## Paso 4: Completar interfaz gráfica:

Arrastramos y solamos un control de tipo `Button` y escribimos `Buscar`:
![SJP APP](/demo/docs/assets/image10.png)

Arrastramos un control de tipo `Title` 
![SJP APP](/demo/docs/assets/image11.png)
escribimos `Resultados:`
![SJP APP](/demo/docs/assets/image12.png)

![SJP APP](/demo/docs/assets/image13.png)
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


![SJP APP](/demo/docs/assets/image36.png)
![SJP APP](/demo/docs/assets/image37.png)
![SJP APP](/demo/docs/assets/image38.png)
![SJP APP](/demo/docs/assets/image39.png)
![SJP APP](/demo/docs/assets/image40.png)
![SJP APP](/demo/docs/assets/image41.png)
![SJP APP](/demo/docs/assets/image42.png)
![SJP APP](/demo/docs/assets/image43.png)
![SJP APP](/demo/docs/assets/image44.png)
![SJP APP](/demo/docs/assets/image45.png)
![SJP APP](/demo/docs/assets/image46.png)
![SJP APP](/demo/docs/assets/image47.png)
![SJP APP](/demo/docs/assets/image48.png)
![SJP APP](/demo/docs/assets/image49.png)
![SJP APP](/demo/docs/assets/image50.png)
![SJP APP](/demo/docs/assets/image51.png)
![SJP APP](/demo/docs/assets/image52.png)
![SJP APP](/demo/docs/assets/image53.png)
![SJP APP](/demo/docs/assets/image54.png)
![SJP APP](/demo/docs/assets/image55.png)
![SJP APP](/demo/docs/assets/image56.png)
![SJP APP](/demo/docs/assets/image57.png)
![SJP APP](/demo/docs/assets/image58.png)
![SJP APP](/demo/docs/assets/image59.png)
![SJP APP](/demo/docs/assets/image60.png)
![SJP APP](/demo/docs/assets/image61.png)
![SJP APP](/demo/docs/assets/image62.png)
![SJP APP](/demo/docs/assets/image63.png)
![SJP APP](/demo/docs/assets/image64.png)
![SJP APP](/demo/docs/assets/image65.png)
![SJP APP](/demo/docs/assets/image66.png)
![SJP APP](/demo/docs/assets/image67.png)
![SJP APP](/demo/docs/assets/image68.png)
![SJP APP](/demo/docs/assets/image69.png)
![SJP APP](/demo/docs/assets/image70.png)
![SJP APP](/demo/docs/assets/image71.png)
![SJP APP](/demo/docs/assets/image72.png)
![SJP APP](/demo/docs/assets/image73.png)
![SJP APP](/demo/docs/assets/image74.png)
![SJP APP](/demo/docs/assets/image75.png)
![SJP APP](/demo/docs/assets/image76.png)
![SJP APP](/demo/docs/assets/image77.png)
![SJP APP](/demo/docs/assets/image78.png)
![SJP APP](/demo/docs/assets/image79.png)
![SJP APP](/demo/docs/assets/image80.png)
![SJP APP](/demo/docs/assets/image81.png)
![SJP APP](/demo/docs/assets/image82.png)
![SJP APP](/demo/docs/assets/image83.png)
![SJP APP](/demo/docs/assets/image84.png)
![SJP APP](/demo/docs/assets/image85.png)
![SJP APP](/demo/docs/assets/image86.png)
![SJP APP](/demo/docs/assets/image87.png)
![SJP APP](/demo/docs/assets/image88.png)
![SJP APP](/demo/docs/assets/image89.png)
![SJP APP](/demo/docs/assets/image90.png)
![SJP APP](/demo/docs/assets/image91.png)
![SJP APP](/demo/docs/assets/image92.png)
![SJP APP](/demo/docs/assets/image93.png)
![SJP APP](/demo/docs/assets/image94.png)
![SJP APP](/demo/docs/assets/image95.png)
![SJP APP](/demo/docs/assets/image96.png)
![SJP APP](/demo/docs/assets/image97.png)
![SJP APP](/demo/docs/assets/image98.png)
![SJP APP](/demo/docs/assets/image99.png)
![SJP APP](/demo/docs/assets/image100.png)
![SJP APP](/demo/docs/assets/image101.png)
![SJP APP](/demo/docs/assets/image102.png)
![SJP APP](/demo/docs/assets/image103.png)
![SJP APP](/demo/docs/assets/image104.png)
![SJP APP](/demo/docs/assets/image105.png)
![SJP APP](/demo/docs/assets/image106.png)
![SJP APP](/demo/docs/assets/image107.png)
![SJP APP](/demo/docs/assets/image108.png)
![SJP APP](/demo/docs/assets/image109.png)

