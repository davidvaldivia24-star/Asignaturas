#Parte 1. Trabajo individual
En esta parte se ha dedicado a: 
# 1. Clonar el repositorio desde GitHub a local
	git clone https://github.com/tu-usuario/practica-git-parte1-tu-nombre.git
	cd practica-git-parte1-tu-nombre

# 2. Crear archivo presentacion.md con tu nombre y breve presentación
	echo "# Presentación" > presentacion.md
	echo "Mi nombre es David y soy estudiante de DAM." >> presentacion.md
	#aqui se crean lo archivos para posteriormente añadirlo al main y guardar las actualizaciones.
	
# 3. Añadir al stage, commit y push
	git add presentacion.md
	git commit -m "feat: añade archivo de presentación" #actualizaciones
	git push origin main #vincula con GitHub.
	
#Ejercicio 2: Trabajo en ramas
#1. Crear nueva rama feature-hobbies
	git checkout -b feature-hobbies

# 2. Editar presentacion.md y añadir hobbies
	echo "- Los hobbies " >> presentacion.md

# 3. Commit y subir al remoto
	git add presentacion.md
	git commit -m "añade sección de hobbies"
	git push -u origin feature-hobbies

# 4. Cambiar a main y fusionar
	git checkout main
	git merge feature-hobbies
	git push origin main	
	
##En esta tarea de creo y trabaho sobre una rama adicional a la principal para posterioremente fusionar las dos e integrar los cambios realizados y los posibles conflictos que se hayan podido crear.

#Ejercicio 3: Conflictos y resolución
#comandos:
	git push origin main
	git pull origin main

	git add presentacion.md
	git commit -m "resuelve conflicto con cambios en GitHub"
	git push origin main
#Resumen:
## Se resuelve el conflicto trayendo el proyecto de GitHub y haciendo commit.

# Ejercicio 4: Logs y diffs

# Primer commit de notas.md
git add notas.md
git commit -m "docs: añade repaso de conceptos de Git"

# Segundo commit
git add notas.md
git commit -m "docs: añade ejercicio de práctica de commits"

# Ver historial resumido con gráfico
git log --oneline --graph --all

# Ver cambios entre los últimos commits
git diff HEAD~1 HEAD

## Resumen: Saca por pantalla un historial resumido de todos los commits y también muestra los cambios realizados en los ultimos commit.

## Ejercicio 5: Conflictos intencionados

# Crear rama para conflicto
git checkout -b feature-conflicto

# Modificar la misma línea en feature-conflicto
git add notas.md
git commit -m "cambia línea en feature-conflicto"

# Cambiar a main y modificar la misma línea
git checkout main
git add notas.md
git commit -m "cambia línea en main"

# Intentar fusionar y resolver conflicto
git merge feature-conflicto

# Resolución manual en notas.md:
# Se va al archivo y te mostrará el conflicto que tiene ya que muestra las dos versiones que tiene en el que habrá que elegir la mejor opcion o fusionarla.
#posteriormente se hace commit.
git add notas.md
git commit -m "fix: resuelve conflicto entre main y feature-conflicto"

# Documentar resolución
echo "# Resolución del conflicto en notas.md" > conflicto.md
echo "Se combinó la línea de main y feature-conflicto." >> conflicto.md
git add conflicto.md
git commit -m "docs: documenta resolución de conflicto"
git push


## Ejercicio 6: Tags
# Crear tag ligero
git tag v1.0
git push origin --tags

# Crear tag anotado
git tag -a v1.1 -m "Primera versión estable"
git push origin --tags

# Ver tags
git tag
git show v1.1

# Resumen: Puedes identificar los commits con tag, en el que por ejemplo puedes poner versiones (v1.0, v1.1etc..)
