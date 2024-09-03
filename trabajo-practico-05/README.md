# Trabajo Práctico 5 - Despliegue de aplicaciones con Azure Devops Release Pipelines

Cetti Paolo (2223989)

# Desarrollo:
4.1\. Crear una cuenta en Azure

![](image.png)

4.2\. Crear un recurso Web App en Azure Portal y navegar a la url provista

4.3\. Actualizar Pipeline de Build para que use tareas de DotNetCoreCLI@2 como en el pipeline clásico, luego crear un Pipeline de Release en Azure DevOps con CD habilitada

4.4\. Optimizar Pipeline de Build

4.5\. Verificar el deploy en la url de la WebApp /weatherforecast

4.6\. Realizar un cambio al código del controlador para que devuelva 7 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio

4.7\. Clonar la Web App de QA para que contar con una WebApp de PROD a partir de un Template Deployment en Azure Portal y navegar a la url provista para la WebApp de PROD.

4.8\. Agregar una etapa de Deploy a Prod en Azure Release Pipelines 

4.9\.  Realizar un cambio al código del controlador para que devuelva 10 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast se muestra lo mismo.

4.10\. Modificar pipeline de release para colocar una aprobación manual para el paso a Producción.

4.11\. Realizar un cambio al código del controlador para que devuelva 5 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast aun se muestra la versión anterior.

4.12\. Aprobar el pase ya sea desde el release o desde el mail recibido. 
<img width="1197" alt="image" src="https://github.com/user-attachments/assets/05e8d1a1-ae06-4824-91d7-1a6e0162e859">

<img width="1221" alt="image" src="https://github.com/user-attachments/assets/33710115-a5c3-43ee-a208-5879331c7a8d">

<img width="1466" alt="image" src="https://github.com/user-attachments/assets/9655c548-d3da-4d29-8080-8324d711c18f">

4.12.1\. Notar que se puede dar la aprobación pero posponer su aplicación hasta una determinada fecha


<img width="1222" alt="image" src="https://github.com/user-attachments/assets/11f710b9-4ac1-4e2c-a560-7714835b2ce6">

4.13\. Esperar a la finalización de la etapa de Pase a Prod y luego corroborar que en la url de la webapp_prod/weatherforecast se muestra la nueva versión coinicidente con la de QA.
<img width="1465" alt="image" src="https://github.com/user-attachments/assets/533ac589-58e1-4f36-9356-d37a0da58220">

<img width="1125" alt="image" src="https://github.com/user-attachments/assets/26256e9d-28c5-41d7-97cb-e86df429e817">

4.14\. Realizar un pipeline (no release) que incluya el deploy a QA y a PROD con una aprobación manual. El pipeline debe estar construido en YAML sin utilizar el editor clásico de pipelines ni el editor clásico de pipelines de release.
 