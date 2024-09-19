## Trabajo Práctico 7 - Code Coverage, Análisis estático de Código y Pruebas de Integración

CETTI Paolo (2223989)

Proyecto de Azure DevOps: https://dev.azure.com/cettipao/Angular-CRUD

#### 4.1 Agregar Code Coverage a nuestras pruebas unitarias de backend y front-end e integrarlas junto con sus resultados en nuestro pipeline de build.
- Desarrollo del punto 4.1: 
	- ##### 4.1.1 En el directorio raiz de nuestro proyecto Angular instalar el siguiente paquete:

![](image.png)

 - ##### 4.1.2 Editar nuestro archivo karma.conf.js para que incluya reporte de cobertura

 ![](image-1.png)

 - ##### 4.1.3 En el dir raiz del proyecto EmployeeCrudApi.Tests ejecutar:

 ![](image-2.png)

 - ##### 4.1.4 Agregar a nuestro pipeline ANTES del Build de Back la tarea de test con los argumentos especificados y la de publicación de resultados de cobertura:

![](image-3.png)

 - ##### 4.1.5 Agregar a nuestro pipeline ANTES del Build de front la tarea de test y la de publicación de los resultados.

![](image-4.png)

 - ##### 4.1.6 Ejecutar el pipeline y analizar el resultado de las pruebas unitarias y la cobertura de código.

 ![](image-5.png)

 ![	](image-6.png)

#### 4.2 Agregar Análisis Estático de Código con SonarCloud:

##### 4.2.1 Integraremos SonarCloud para analizar el código fuente. Configurar SonarCloud en nuestro pipeline siguiendo instructivo 5.1

* Antes de nuestra tarea de Build del Back:

![](image-7.png)

* Despues de nuestra tarea de Build del Back:

![](image-8.png)

##### 4.2.2 Vemos el resultado de nuestro pipeline, en extensions tenemos un link al análisis realizado por SonarCloud

![](image-9.png)

##### 4.2.3 Ir al link y analizar toda la información obtenida. Detallar en la entrega del TP los puntos más relevantes del informe, qué significan y para qué sirven.

![](image-10.png)

### Análisis de SonarCloud

- **Total de issues:** 7 (47 min de esfuerzo)
- **Categorías:** Code Smells (Mantenibilidad, Fiabilidad) y Vulnerabilidad de Seguridad.

#### Puntos relevantes:

1. **Vulnerabilidad de Seguridad (Blocker):**  
   Contraseña expuesta en `appsettings.json`.  
   **Solución:** Cambiar y eliminar la contraseña del código.

2. **Code Smells:**  
   - **_context no es readonly** en `EmployeeController.cs`.  
   **Solución:** Declarar `_context` como `readonly`.
   - **Propiedades de valor deben ser anulables o requeridas** en `Employee.cs`.  
   **Solución:** Usar `nullable` o `JsonRequired`.
   - **Await en RunAsync** en `Program.cs`.  
   **Solución:** Añadir `await` para asegurar correcta ejecución asíncrona.

#### Esfuerzo total: 47 min (30 min para la vulnerabilidad).


#### 4.3 Pruebas de Integración con Cypress:

##### 4.3.1 En el directorio raiz de nuestro proyecto Angular instalar el siguiente paquete:

![](image-11.png)

##### 4.3.2 Abrir Cypress:

![](image-12.png)

##### 4.3.3 Inicializar Cypress en nuestro proyecto como se indica en el instructivo 5.2

![](image-13.png)

![](image-14.png)

![](image-15.png)

![](image-16.png)

![](image-17.png)

![](image-18.png)

![](image-19.png)

Esto creará automáticamente una estructura de carpetas dentro de tu proyecto.

![](image-20.png)

##### 4.3.4 Crear nuestra primera prueba navegando a nuestro front.

En la carpeta cypress/e2e, crear un archivo con el nombre primer_test.js y agregar el siguiente código para probar la página de inicio de nuestro front:

![](image-21.png)

![](image-22.png)

4.3.5 Correr nuestra primera prueba

Ejecutamos la prueba en cypress:

![](image-23.png)

También es posible ejecutar Cypress en modo "headless" (sin interfaz gráfica) utilizando el siguiente comando:

![](image-24.png)

##### 4.3.6 Modificar nuestra prueba para que falle.
* Editamos el archivo primer_test.cy.js y hacemos que espere otra cosa en el título

![](image-25.png)

* Ejecutamos cypress en modo headless

Ejecutamos y verificamos que dio error

![](image-26.png)

Observamos el screenshot que saco

![](image-27.png)

##### 4.3.6 Grabar nuestras pruebas para que Cypress genere código automático y genere reportes:
* Cerramos Cypress
* Editamos el archivo cypress.config.ts incluyendo la propiedad experimentalStudio en true y la configuración de reportería.

![](image-28.png)

* Corremos nuevamente Cypress con npx cypress open, una vez que se ejecute nuestra prueba tendremos la opción de "Add Commands to Test". Esto permitirá interactuar con la aplicación y generar automáticamente comandos de prueba basados en las interacciones con la página:

![](image-29.png)

Por ejemplo, si agregamos un nuevo empleado y luego verificamos que esté en la lista, Cypress nos generará un código como este:

![](image-36.png)

Por supuesto que habrá que hacerle ajustes, como por ejemplo que se fije siempre en la última fila de la grilla y no en la posición 15 como lo grabó, es ahí cuando consultando la documentación de Cypress debemos ver cómo modificar el código, en nuestro caso de ejemplo sería así:

![](image-37.png)

##### 4.3.7 Hacemos prueba de editar un empleado
* Creamos en cypress/e2e/ un archivo editEmployee_test.cy.js con el siguiente contenido, guardamos y aparecerá en Cypress:

![](image-31.png)

![](image-32.png)

- Hacemos "Add command to the test" y empezamos a interactuar con la página

![](image-33.png)

Hacemos algunos ajustes al código generado:

![](image-34.png)

Observamos que se ejecuta correctamente

![](image-35.png)

#### 4.4 Desafíos:
Integrar en el pipeline SonarCloud para nuestro proyecto Angular, mostrar el resultado obtenido en SonarCloud

Para ello previo al build preparamos el SonarCloud

![](image-38.png)

Post-build, publicamos los resultados de sonarcloud

![](image-39.png)

Implementar en Cypress pruebas de integración que incluya los casos desarrollados como pruebas unitarias del front en el TP06.

Incorporar al pipeline de Deploy la ejecución de las pruebas de integración y la visualización de sus resultados.

Resultado esperado:

* Un Pipeline en YAML que incluya a) Build de QA y Front con ejecución y resultado de pruebas de code coverage, pruebas unitarias y análisis de Sonar Cloud y b) Deploy a WebApp(s) de QA y Front que incluya ejecución y resultado de pruebas de integración

* Dos Stages: Una para Build, Test Unitarios, Code Coverage y SonarCloud y otra para el Deploy a QA con Tests de Integración

* En la pestaña Test, poder visualizar los Test Unitarios de Front y Back y los Test de Integracion:

* En la pestaña Code Coverage, visualizar la cobertura de las pruebas unitarias de Back y de Front:

* En la pestaña Extensions, ver el análisis de SonarCloud en verde

* Un documento de una carilla explicando qué información pudieron sacar del análisis de Sonar Cloud y de las pruebas de cobertura.