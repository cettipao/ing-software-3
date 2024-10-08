## Trabajo Práctico 3 - Introducción a Azure Devops

 **¿Qué es Azure DevOps?**

**Azure DevOps** es un conjunto de herramientas de Microsoft diseñado para facilitar la colaboración en el desarrollo de software. Incluye servicios para la planificación de proyectos, la gestión del código fuente, la integración continua y la entrega continua (CI/CD), la gestión de pruebas y la implementación en la nube. Las principales herramientas dentro de Azure DevOps son Azure Repos (control de versiones), Azure Pipelines (CI/CD), Azure Boards (gestión de proyectos), Azure Test Plans (pruebas) y Azure Artifacts (gestión de paquetes).

#### Beneficios de utilizar Azure DevOps:

1. **Integración con el ecosistema de Microsoft**: Azure DevOps se integra fácilmente con herramientas de Microsoft como Visual Studio, GitHub, y Azure, lo que simplifica la implementación en entornos de desarrollo que ya utilizan estas tecnologías.

2. **Versatilidad y flexibilidad**: Admite una amplia gama de lenguajes de programación, plataformas y entornos de despliegue, lo que permite a los equipos trabajar con sus tecnologías preferidas.

3. **Automatización completa del ciclo de vida del desarrollo**: Facilita la implementación de prácticas DevOps como CI/CD, mejorando la eficiencia y reduciendo los errores en el proceso de entrega de software.

4. **Escalabilidad**: Azure DevOps es adecuado tanto para proyectos pequeños como para grandes organizaciones con múltiples equipos de desarrollo.

5. **Integración con herramientas de terceros**: Además de las herramientas de Microsoft, se puede integrar con otras soluciones como Jira, Jenkins, Docker, Kubernetes, entre otros.

6. **Seguridad y control**: Ofrece control granular sobre los permisos de acceso y la gestión de código, además de cumplir con estándares de seguridad y cumplimiento de la industria.

#### Pasos del TP
 - 3.1 Crear una cuenta en Azure DevOps
 ![](img/image.png)

 - 3.2 Crear un proyecto Sample01
 
![](img/image-1.png)
![](img/image-2.png)

 - 3.3 Crear un repo GIT desde cero

![](img/image-3.png)
![](img/image-4.png)

 - 3.4 Crear un proyecto Sample02

![](img/image-5.png)
![](img/image-6.png)

 - 3.5 Importar un repo desde GitHub: https://github.com/ingsoft3ucc/SimpleWebAPI.git

![](img/image-7.png)
![](img/image-8.png)
![](img/image-9.png)
![](img/image-10.png)
![](img/image-11.png)
![](img/image-12.png)

 - 3.6 Realizar un cambio en un archivo, y subirlo al repo de ADO.

 Creo un Repo nuevo (ing-software-3) e inicializo un repo

 ![](img/image-13.png)

 Consigo el link para clonarlo y lo clono en mi pc

 ![](img/image-14.png)
 ![](img/image-15.png)

 Cambio el readme, commit y push
 ![](img/image-16.png)
 ![](img/image-17.png)

 Verifico el cambio en el repo

 ![](img/image-18.png)

 - 3.7 Crear un pipeline, solicitar acceso a jobs de paralelismo

![](img/image-19.png)
![](img/image-20.png)
![](img/image-21.png)
![](img/image-22.png)
![](img/image-23.png)
![](img/image-24.png)
![](img/image32.png)

 - 3.8 Cambiar el tipo de proceso de Basic a Agile

![](img/image-25.png)
![](img/image-26.png)
![](img/image-27.png)

 - 3.8 Crear un sprint

![](img/image-28.png)

 - 3.9 Crear User Stories

 ![](img/image-29.png)

 - 3.10 Crear Tasks y Bugs

![](img/image-31.png)
![](img/image-30.png)

#### 4- Presentación del trabajo práctico.
Subir un al repo con las capturas de pantalla de los pasos realizados y colocar en el excel de repos (https://docs.google.com/spreadsheets/d/1mZKJ8FH390QHjwkABokh3Ys6kMOFZGzZJ3-kg5ziELc/edit?gid=0#gid=0) la url del proyecto de AzureDevops