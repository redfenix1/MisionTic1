# Comandos GIT para conectarse
## Configuración inicial
```
git config --global user.name "nombre de usuario"
git config --global user.email "correo@dominio.com"
```
## Clonar un repo
1. Crear una carpeta en el equipo, ubicarse en ella y abrir git-bash ```clic derecho > git-bash```
```
git init
```
2. Clonar el repositorio
```
git clone https://github.com/redfenix1/MisionTicGrupo.git
```
3. Moverse a la carpeta
```
cd MisionTicGrupo
```
>Ver que pasa de ```master``` a ```main```
## Vincular con Github
```
git remote add origin https://github.com/redfenix1/MisionTicGrupo.git
```
## Trabanajo con Branch
1. Consultar los branch
```
git branch
```
2. Crear el branch
```
git branch nombre_del_nuevo_branch
```
3. Entrar al branch
```
git checkout nombre_del_nuevo_branch
```
## Verificar las conexiones remotas
```
git remote -v
```
>Generalmente hay una conexión que se llama ```origin``` y debe tener la direccion del git, por lo general trabajaremos con esa.
## *Opcional:* Crear nueva conexión
```
git remote add nombre_conexion https://github.com/example/repository.git
```
## Trabajando en el branch
1. Actualizamos la conexión del nuevo branch
```
git branch -u origin/nombre_del_nuevo_branch
```
> **origin** es la conexión por defecto, puede usar alguna otra por ejemplo: ```git branch -u nombre_conexion/nombre_del_nuevo_branch``` <br> <br> Siempre se debe realizar para poder hacer ```git pull``` a algún branch
<br>
<br>

***

# Comandos GIT para subir, bajar datos y otros
## Bajar archivos
1. Bajar datos del repository(remoto) al working directory(local)
```
git pull
```
> Siempre debe ser el primer comando en usarse, y sirve para bajar los datos de Github a nuestro entorno local
## Subir archivos
1. Pasar los datos a staging area
```
git add ARCHIVO.txt       #Sirve para pasar un solo archivo
git add *.txt             #Sirve para pasar todos los archivos que terminen en .txt
git add --all             #Sirve para pasar todos los archivos
```
2. **Opcional:** Remover archivos del staging area
```
git restore --staged ARCHIVO.txt
```
3. Pasar los archivos al repositorio(local)
```
git commit -m "Mensaje de registro para el commit"
```
>El mensaje debe identificar brevemente los cambios realizados en este cargue de información
4. Pasar los archivos del repositorio(loca) al repositorio(remoto)
```
git push
```
## Otros comandos
1. Comando para ver los archvivos pendientes por enviar al staging area
```
git status
```
2. Comando para ver los commit realizados
```
git log
```
3. Comando para ver las diferencias
```
git diff nombre_del_archivo       #Entre archivos (working directory vs. repository (local))
git diff branch1..branch2         #Comparar dos branch
```
4. Eliminar archivos
```
git rm ARCHIVO.txt                #Elimina el archivo del repository
rm ARCHIVO.txt                    #ELimina el archivo de forma local, sirve para los archivos que no están en el staging area
```
# Comandos GIT para combinar ramas
## Unir ramas
```
git checkot rama_principal                  #Es la rama donde va a quedar la información
git merge rama_secundaria                   #Es la rama que queremos fusionar con la principal
```
## _CUIDADO_ Eliminar ramas
```
git branch -d nombre_del_branch
```
>Se recomienda eliminar las ramas que no se necesiten, teniendo precauión que la información se ha subido
