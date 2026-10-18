# Ejercicio 1: Introducción a Git y GitHub

## Apartado 14: repositorio prueba2_ladysoria

### 1. Crear el repositorio local en Windows
```
mkdir prueba2_ladysoria
cd prueba2_ladysoria
git init
echo "Contenido del archivo 1" > archivo1.txt
echo "Contenido del archivo 2" > archivo2.txt
git add .
git commit -m "añadir dos ficheros"
```

### 2. Conectar con GitHub y subirlo
```
git remote add origin https://github.com/Ladysoria/prueba2_ladysoria.git
git push -u origin master
```

### 3. Clonar en la máquina Linux Debian
```
git clone https://github.com/Ladysoria/prueba2_ladysoria.git
```

### 4. Modificar un archivo y crear archivo3.txt en Windows
```
echo "Texto modificado" >> archivo1.txt
echo "Contenido del archivo 3" > archivo3.txt
git add .
git commit -m "modifique el fichero"
git push
```

### 5. Actualizar en Linux Debian
```
git pull
```