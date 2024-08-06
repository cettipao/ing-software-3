# Trabajo Practico 1
Cetti Paolo (2223989)

### 1. Instalar Git
![alt text](img/34.png)

### 2. Crear un repositorio local y agregar archivos
1. Crear un repositorio local:
![alt text](img/35.png)
2. Agregar un archivo `README.md` con contenido:
![alt text](img/36.png)
![alt text](img/37.png)
3. Hacer un commit con un mensaje descriptivo:
![alt text](img/38.png)
### 3. Configuración del Editor Predeterminado
![alt text](img/39.png)

### 4. Creación de Repos 01 -> Crearlo en GitHub, clonarlo localmente y subir cambios
1. Crear una cuenta en GitHub
2. Crear un nuevo repositorio en GitHub con `README.md` por defecto.
![alt text](img/0.png)
3. Clonar el repositorio remoto:
Copiamos la url del repo
![alt text](img/1.png)
Clonamos
![alt text](img/2.png)
4. Editar el archivo `README.md`:
![alt text](img/5.png)
Verificamos el cambio con git status
![alt text](img/6.png)
5. Crear el archivo `.gitignore`:
![alt text](img/7.png)
6. Hacer commit y push:
![alt text](img/8.png)
![alt text](img/9.png)

### 5. Creación de Repos 02 -> Crearlo localmente y subirlo a GitHub
1. Crear un repositorio local:
![alt text](img/10.png)
2. Agregar archivo `README.md`:
![alt text](img/11.png)
![alt text](img/12.png)
3. Crear repositorio en GitHub.
![alt text](img/13.png)
4. Asociar repo local con remoto:
![alt text](img/14.png)
5. Crear archivo `.gitignore`:
![alt text](img/15.png)
6. Hacer commit y push:
![alt text](img/16.png)
![alt text](img/17.png)

### 6. Ramas
1. Crear una nueva rama:
![alt text](img/18.png)
2. Cambiarse a esa rama:
![alt text](img/19.png)
3. Hacer un cambio en `README.md` y hacer commit:
![alt text](img/20.png)
![alt text](img/21.png)
4. Revisar diferencias entre ramas:
![alt text](img/22.png)

### 7. Merges
1. Hacer un merge FF (fast-forward):
![alt text](img/23.png)
2. Borrar la rama creada:
![alt text](img/24.png)
3. Ver el log de commits:
![alt text](img/25.png)

4. Repetir el ejercicio 6 para hacer un merge con No-FF:
![alt text](img/26.png)
![alt text](img/27.png)
![alt text](img/28.png)
![alt text](img/29.png)
![alt text](img/30.png)

### 8. Resolución de Conflictos
* Instalar alguna herramienta de comparación:
Usaré la que trae Visual Studio Code ya que ya lo tengo configurado asi en el git

* Crear una nueva rama conflictBranch:
![alt text](img/40.png)

* Modificar `README.md` desde `main` y commitear:
![alt text](img/42.png)
![alt text](img/41.png)
![alt text](img/43.png)

* Modificar la misma línea desde `conflictBranch` y commitear:
![alt text](img/45.png)
![alt text](img/44.png)
![alt text](img/46.png)
* Ver diferencias:
![alt text](img/47.png)
![alt text](img/48.png)
* Intentar mergear y resolver conflicto:
![alt text](img/50.png)
![alt text](img/49.png)
![alt text](img/51.png)

### 9. Familiarizarse con el concepto de Pull Request
1. Un Pull Request es una función de GitHub que permite a tu equipo solicitar la revisión y aprobación de sus cambios antes de fusionarlos en la rama principal de desarrollo, denominada “master” o “main”.
2. Crear un branch local y agregar cambios:
![alt text](img/18.png)
![alt text](img/19.png)
![alt text](img/20.png)
![alt text](img/21.png)
3. Crear un pull request en GitHub y completar el proceso de revisión y merge.
![alt text](img/31.png)
![alt text](img/32.png)
![alt text](img/33.png)

### 10. Algunos ejercicios online
1. Entrar a [Learn Git Branching](https://learngitbranching.js.org/).
2. Completar los ejercicios de Introduction Sequence.
![alt text](img/52.png)