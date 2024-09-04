# Trabajo Práctico 5 - Despliegue de aplicaciones con Azure Devops Release Pipelines

### Cetti Paolo (2223989)

# Desarrollo:
4.1\. Crear una cuenta en Azure

![](img/image.png)

4.2\. Crear un recurso Web App en Azure Portal y navegar a la url provista

![](img/image-1.png)
![](img/image-2.png)

Creamos un nuevo grupo de recursos

![](img/image-3.png)

Ponemos el nombre, la pila de entorno y la region

![](img/image-4.png)

Creamos el plan MiAppPlan01y utilizamos el plan de precios gratis

![](img/image-5.png)

Pasamos el apartado de base de datos, mantenemos deshabilidata la CI

![](img/image-6.png)

Habilitamos la autenticacion basica y pasamos a redes

![](img/image-7.png)

Pasamos a supervision y proteccion, y deshabilitamos Application Insights

![](img/image-8.png)

Pasamos a Revisar y crear y descargamos la plantilla

![](img/image-9.png)
![](img/image-10.png)
![](img/image-11.png)

Tras arreglar un error de region (no tenia disponible East US con el plan gratuito, cambie a Brazil South).
Se completo Exitosamente la implementacion

![](img/image-12.png)
![](img/image-13.png)

Comprobamos su funcionamiento en https://miwebapp01-cetti.azurewebsites.net/
![](img/image-14.png)

4.3\. Actualizar Pipeline de Build para que use tareas de DotNetCoreCLI@2 como en el pipeline clásico, luego crear un Pipeline de Release en Azure DevOps con CD habilitada

Creamos un nuevo pipeline con el .yaml mandado por whatsapp

![](img/image-15.png)

Vemos que corrio exitosamente

![](img/image-16.png)

Creamos un pipeline de realases

![](img/image-17.png)

Utilizamos el template Azure App Service Deployment

![](img/image-18.png)

Cambiamos el nombre de la etapa a "Deploy a QA"

![](img/image-19.png)

Seleccionamos como artifact el build del pipeline creado con el .yaml nuevo

![](img/image-20.png)

Habilitamos el CI

![](img/image-21.png)

Configuramos las tareas del stage, elegimos nuestra azure subscription y la autorizamos

![](img/image-22.png)

Seleccionamos nuestra web app creada en azure portal

![](img/image-23.png)

Le cambiamos el nombre a ReleasePipeline01

![](img/image-24.png)

4.4\. Optimizar Pipeline de Build

El pipeline del build ya esta optimizado segun el .yaml que nos paso el profe

4.5\. Verificar el deploy en la url de la WebApp /weatherforecast

Creamos una release para probar 

![](img/image-25.png)
![](img/image-26.png)

Fue exitoso

![](img/image-27.png)

4.6\. Realizar un cambio al código del controlador para que devuelva 7 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio

Realizamos el cambio para que devuelva 7 pronosticos
![](img/image-28.png)

Hacemos commit
![](img/image-29.png)

Se ejecuto automatica y exitosamente el pipeline de build
![](img/image-30.png)

Se ejecuto automatica y correctamente el pipeline de release
![](img/image-31.png)

Corroboramos que ahora muestra 7 pronosticos
![](img/image-32.png)

4.7\. Clonar la Web App de QA para que contar con una WebApp de PROD a partir de un Template Deployment en Azure Portal y navegar a la url provista para la WebApp de PROD.

Vamos a crear a partir de template deployment

![](img/image-33.png)

Creamos nuestra propia plantilla
![](img/image-34.png)

Tocamos en cargar archivo y cargamos el template.json descargado previamente
![](img/image-35.png)

Cargamos tambien los parametros y le cambiamos el nombre agregandole PROD
![](img/image-36.png)

Pasamos a Revisar y Crear, y creamos
![](img/image-37.png)

Se implemento exitosamente
![](img/image-38.png)

Corroboramos
![](img/image-39.png)

Mi grupo de recursos quedo
![](img/image-40.png)

4.8\. Agregar una etapa de Deploy a Prod en Azure Release Pipelines 

Vamos a editar el ReleasePipeline01 y clonamos el Deploy a QA
![](img/image-41.png)
![](img/image-42.png)

Le cambiamos el nombre a Deploy a Prod
![](img/image-43.png)

Le cambiamos el app service
![](img/image-44.png)

Seleccionamos Deploy Azure App service y guardamos
![](img/image-45.png)

4.9\.  Realizar un cambio al código del controlador para que devuelva 10 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast se muestra lo mismo.

Realizamos el cambio
![](img/image-46.png)
![](img/image-47.png)

El build pipeline se ejecuto correctamente
![](img/image-48.png)

El release pipeline tambien se ejecuto correctamente
![](img/image-49.png)

Vemos que tanto en QA como el Release se muestran los 10 pronosticos
![](img/image-50.png)

4.10\. Modificar pipeline de release para colocar una aprobación manual para el paso a Producción.

Volvemos a editar el release pipeline y habilitamos el pre-deployment approvals con mi usuario
![](img/image-51.png)

Guardamos esta configuracion

4.11\. Realizar un cambio al código del controlador para que devuelva 5 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast aun se muestra la versión anterior.

Realizamos el cambio y commiteamos
![](img/image-52.png)
![](img/image-53.png)

Se ejecuto correctamente el pipeline de build
![](img/image-54.png)

Se ejecuto correctamente el pipeline de release en QA y esta esperando aprobacion
![](img/image-55.png)

Notamos que en QA muestra 5 pronosticos pero en Prod sigue mostrando los 10
![](img/image-56.png)

4.12\. Aprobar el pase ya sea desde el release o desde el mail recibido. 

Verificamos el mail
![](img/image-57.png)

Aprobamos el release
![](img/image-58.png)
![](img/image-59.png)

Vemos que en este Release4 se hizo el deploy a Prod
![](img/image-60.png)

4.12.1\. Notar que se puede dar la aprobación pero posponer su aplicación hasta una determinada fecha

![](img/image-62.png)

4.13\. Esperar a la finalización de la etapa de Pase a Prod y luego corroborar que en la url de la webapp_prod/weatherforecast se muestra la nueva versión coinicidente con la de QA.

Corroboramos que ahora en prod muestra 5 pronosticos
![](img/image-61.png)

4.14\. Realizar un pipeline (no release) que incluya el deploy a QA y a PROD con una aprobación manual. El pipeline debe estar construido en YAML sin utilizar el editor clásico de pipelines ni el editor clásico de pipelines de release.
 
Vamos a Pipelines y creamos uno nuevo, no usamos el clasico
![](img/image-63.png)
![](img/image-64.png)
![](img/image-65.png)

Usamos el siguiente .yaml con los stages (pongo el .yaml completo al final del md)
![](img/image-67.png)

Usamos un Enviroment para poder modificar los usuarios que pueden dar permiso sin modificar el codigo
![](img/image-71.png)
![](img/image-72.png)
Ponemos ese enviroment en el stage de deploy a produccion

Lo guardamos y corremos, nos pide permisos. Le damos los permisos a nuestra subscripcion
![](img/image-66.png)

Vemos como hace el build y deploy en produccion en el stage1 y espera aprobacion para hacer deploy en produccion en el stage2
![](img/image-68.png)

Le damos la aprobacion

![](img/image-70.png)

Se ejecuto correctamente y se hicieron los deploys
![](img/image-73.png)

### El .yaml que use para el 4.14
```yaml 
trigger:
- main

pool:
  vmImage: 'ubuntu-latest'

variables:
  solution: 'SimpleWebAPI.sln'
  buildPlatform: 'Any CPU'
  buildConfiguration: 'Release'
  ConnectedServiceName: 'Azure subscription 1 (de2100ee-d1a0-44f9-90cf-bfd824766f52)' # Subscription ID
  WebAppKind: 'webApp'
  DevWebAppName: 'MiWebApp01-cetti' # QA WebApp name
  ProdWebAppName: 'MiWebApp01-cetti-PROD' # Production WebApp name

stages:
- stage: Build
  displayName: 'Build Application'
  jobs:
  - job: Build
    displayName: 'Build Application'
    steps:
      - task: UseDotNet@2
        inputs:
          packageType: sdk
          version: '8.x'  # Use the correct version of .NET
          installationPath: $(Agent.ToolsDirectory)/dotnet

      - script: |
          echo "Current directory: $(Build.SourcesDirectory)"
          cd $(Build.SourcesDirectory)
          ls -l
          dotnet restore $(solution)
        displayName: 'Restore NuGet Packages'

      - script: |
          dotnet build $(solution) --configuration $(buildConfiguration)
        displayName: 'Build Project'

      - script: |
          dotnet test $(solution) --configuration $(buildConfiguration)
        displayName: 'Run Unit Tests'

      - script: |
          dotnet publish $(solution) --configuration $(buildConfiguration) --output $(Build.ArtifactStagingDirectory) --no-build
        displayName: 'Publish Project'
      
      - task: PublishBuildArtifacts@1
        inputs:
          pathToPublish: '$(Build.ArtifactStagingDirectory)'
          artifactName: 'drop'
          publishLocation: 'Container'
        displayName: 'Publish Build Artifacts'

- stage: DeployToQA
  displayName: 'Deploy to QA'
  dependsOn: Build
  condition: succeeded()
  jobs:
  - job: DeployToQA
    displayName: 'Deploy to QA'
    steps:
      - task: DownloadPipelineArtifact@2
        displayName: 'Download Build Artifacts'
        inputs:
          buildType: 'current'
          artifactName: 'drop'
          targetPath: '$(Pipeline.Workspace)/drop'

      - script: ls -l "$(Pipeline.Workspace)/drop"
        displayName: 'List Pipeline Workspace Content (QA)'

      - task: AzureRmWebAppDeployment@4
        displayName: 'Deploy to Azure App Service (QA)'
        inputs:
          azureSubscription: '$(ConnectedServiceName)'
          appType: 'webApp'
          WebAppName: '$(DevWebAppName)'
          package: '$(Pipeline.Workspace)/drop'

- stage: DeployToProd
  displayName: 'Deploy to Production'
  dependsOn: DeployToQA
  condition: succeeded()
  jobs:
  - deployment: DeployToProd
    displayName: 'Deploy to Production'
    environment: 'Production'
    strategy:
      runOnce:
        deploy:
          steps:
            - task: DownloadPipelineArtifact@2
              displayName: 'Download Build Artifacts'
              inputs:
                buildType: 'current'
                artifactName: 'drop'
                targetPath: '$(Pipeline.Workspace)/drop'

            - script: ls -l "$(Pipeline.Workspace)/drop"
              displayName: 'List Pipeline Workspace Content (Production)'

            - task: AzureRmWebAppDeployment@4
              displayName: 'Deploy to Azure App Service (Production)'
              inputs:
                azureSubscription: '$(ConnectedServiceName)'
                appType: 'webApp'
                WebAppName: '$(ProdWebAppName)'
                package: '$(Pipeline.Workspace)/drop'


``` 