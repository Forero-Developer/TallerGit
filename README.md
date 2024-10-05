# Taller de Git

Este es un proyecto de práctica para aprender y aplicar los comandos básicos de Git, como inicializar repositorios, crear ramas, realizar commits, hacer merges, y resolver conflictos. A continuación, se detallan los pasos que seguí durante este taller.

## Pasos realizados

1. **Inicialización del repositorio**
   - Inicié un nuevo repositorio vacío:
     ```bash
     git init
     ```

2. **Primer commit**
   - Creé el archivo `README.md` y realicé el primer commit:
     ```bash
     echo "archivo readme" > README.md
     git add README.md
     git commit -m "Primer commit con README"
     ```

3. **Creación de una nueva rama**
   - Creé una rama llamada `feature` para trabajar en una nueva funcionalidad:
     ```bash
     git checkout -b feature
     ```

4. **Trabajando en la nueva rama**
   - Agregué un archivo `archivo.txt` y realicé algunos commits en la rama `feature`:
     ```bash
     echo "Contenido inicial" > archivo.txt
     git add archivo.txt
     git commit -m "Agregar archivo.txt en feature"
     
     echo "Texto agregado en feature" >> archivo.txt
     git commit -am "Actualizar archivo.txt en feature"
     ```

5. **Fusión de la rama `feature` en `master`**
   - Cambié de nuevo a la rama `master` y realicé un merge con los cambios de `feature`:
     ```bash
     git checkout master
     git merge feature
     ```

6. **Creación de una rama `hotfix`**
   - Creé una rama `hotfix` para solucionar un problema urgente y apliqué los cambios a `master`:
     ```bash
     git checkout -b hotfix
     echo "Solución de error" >> archivo.txt
     git commit -am "Aplicar hotfix"
     
     git checkout master
     git cherry-pick hotfix
     ```

7. **Resolución de conflictos**
   - Resolví un conflicto de merge al combinar cambios de diferentes ramas:
     ```bash
     git merge feature
     # Resolví el conflicto, agregué el archivo y realicé el commit.
     git add archivo.txt
     git commit -m "Resolver conflicto de merge"
     ```

8. **Publicación en un repositorio remoto**
   - Agregué un repositorio remoto y subí los cambios de la rama `master`:
     ```bash
     git remote add origin https://github.com/Forero-Developer/TallerGit.git
     git push -u origin master
     ```