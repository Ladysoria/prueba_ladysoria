# Ejercicio 3: Git. Trabajando con ramas y uniones

## 1. Crear la rama primera y comprobar que existe

```
git branch primera
git branch
```

![Crear la rama primera y comprobarla](images/ej3_rama_primera.png)

## 2. Crear un fichero en la rama primera y fusionarlo con la principal

```
git checkout primera
nano primera.txt
git add primera.txt
git commit -m "Creo primera.txt en la rama primera"
git checkout main
git merge primera
```

![Fichero en la rama primera y fusión con main](images/ej3_merge_primera.png)

**¿Se ha producido conflicto?** No. En la rama primera solo se ha **añadido** un fichero nuevo que no existía en la rama main, por lo que Git simplemente lo incorpora a la rama principal (*Fast-forward*). Los conflictos solo aparecen cuando se modifica la misma parte de un fichero en dos ramas diferentes.

## 3. Borrar la rama primera

```
git branch -d primera
git branch
```

![Borrar la rama primera](images/ej3_borrar_primera.png)

## 4. Crear la rama segunda y producir un conflicto

```
nano prueba.txt
git add prueba.txt
git commit -m "Creo prueba.txt en main"
git checkout -b segunda
nano prueba.txt
git commit -am "Modifico prueba.txt en segunda"
git checkout main
nano prueba.txt
git commit -am "Modifico prueba.txt en main"
git merge segunda
```

![Cambios en las dos ramas y conflicto al fusionar](images/ej3_conflicto.png)

Contenido del fichero donde se ha producido el conflicto:

```
$ cat prueba.txt
<<<<<<< HEAD
Hola, buenos días
=======
hola que tal
>>>>>>> segunda
```

![Contenido del fichero en conflicto](images/ej3_cat_conflicto.png)

## 5. Solucionar el conflicto y sincronizar la rama segunda en GitHub

```
nano prueba.txt
git add .
git commit -m "Soluciono el conflicto de prueba.txt"
git push
git push origin segunda
```

Fichero ya solucionado (sin las marcas del conflicto) y commit de la solución:

![Conflicto solucionado y historial de commits](images/ej3_solucion.png)

Rama segunda creada en el repositorio de GitHub:

![Ramas en GitHub](images/ramas.png)
