### Desafio: Deploy de Back y Front en Container Apps

#### Cetti Paolo (2223989)

Para este desafio, realizare un pipeline de un deploy del proyecto en Container Apps y despues creare otro integrador que incluya todos los deploys

1.1 Creamos un Container apps env

![](img/image.png)

![](img/image-1.png)

Creamos el Stage que deploya a QA

![](img/image-2.png)

![](img/image-3.png)

Le agregamos su test de integraicion con la url del front del container app

![](img/image-4.png)

Creamos el Stage de Deploy a Prod (con enviroment para aprobar el deploy)

![](img/image-5.png)

![](img/image-6.png)

Creamos las variables correspondientes

![](img/image-7.png)

Ejecutamos y vemos que ejecuto exitosamente el despliegue a QA

![](img/image-8.png)

Vemos en el env que se crearon los dos container apps

![](img/image-9.png)

Abrimos el front y vemos que funciona con la api_url bien seteada

![](img/image-10.png)

Le damos permisos para deployar a prod

![](img/image-11.png)

Deploya en prod exitosamente y corroboramos

![](img/image-12.png)

![](img/image-13.png)

![](img/image-14.png)

### Desafio Integrador

Ahora vamos a volver a hacer el integrador pero agregandole Container Apps

Para eso, hacemos 2 templates con los stages de deploy recien hechos

![](img/image-15.png)

Los agregamos al nuevo tp integrador con todos los templates (No hago el deploy a ACI para que no me sigan cobrando, se hizo en el TP9 igual)

![](img/image-16.png)

Todas las variables

![](img/image-17.png)

!![](img/image-18.png)

Ejecutamos el pipeline correctamente (sin ACI para que no me cobren, ya lo hice en el integrador TP9)

![](img/image-19.png)

Le damos los permisos para deploy a prod

![](img/image-20.png)

Se ejecuta todo exitosamente

![](img/image-21.png)


Asi se ve el pipeline con ACI descomentado

![](img/image-22.png)
