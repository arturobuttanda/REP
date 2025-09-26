#  Tarea 4

## Diferencias entre conda, venv y pip.

### 1. pip (Package Installer for Python)

ROL: Es el gestor de paquetes estándar. Su única función es instalar, desinstalar y gestionar librerías (paquetes) de Python.

ALCANCE: Solo maneja paquetes que están en el índice PyPI. No maneja dependencias que no sean de Python (como archivos binarios o librerías de sistema).

COMANDO TÍPICO: pip install [paquete]

### 2. venv (Virtual Environment)
ROL: Es el creador y gestor de entornos virtuales integrado en Python.

FUNCIÓN: Aísla un proyecto al crear una copia limpia del intérprete de Python, evitando conflictos de librerías entre proyectos.

INSTALACIÓN: No instala paquetes; solo crea el aislamiento. Una vez activo, debes usar pip para instalar librerías dentro de él.

COMANDO TÍPICO: python -m venv .venv

### 3. conda (Gestor de Entornos y Paquetes)
ROL: Es un gestor de paquetes Y un gestor de entornos que no se limita a Python. Es más potente para la ciencia de datos.

FUNCIÓN: Puede aislar el proyecto y a la vez instalar paquetes de Python y de otros lenguajes (R, Julia). Su mayor ventaja es su capacidad para manejar dependencias de sistema complejas (binarios, compiladores).

INDIVIDUALIDAD: Conda es una herramienta separada (parte de Anaconda/Miniconda) y no depende de la instalación de Python de tu sistema operativo.

COMANDO TÍPICO: conda create -n [nombre], conda install [paquete]

### Resumen rapido.
venv se usa para aislar tu proyecto (la "caja").

pip se usa para llenar esa caja con librerías de Python.

conda puede hacer ambas cosas y es mejor para dependencias difíciles o multi-lenguaje.

## Pasos a seguir para recrear el entorno en otra computadora

### 1.- Verificar que se tiene instalado conda.
conda --version
conda env list

### 2.- Preparación

Ejemplo: Navegar a la carpeta de tu repositorio
cd C:\Mi_proyect\mi_proyecto

### 3.- Crear el nuevo entorno Conda.
Crea el nuevo entorno en esta máquina. Es crucial usar la misma versión de Python que tenías originalmente (si la recuerdas, si no, usa una estable como 3.11).

conda create --name [nombre_del_entorno] python=[version]
 *Ejemplo:
conda create --name nuevo_entorno python=3.11

Confirma con y cuando se te solicite.

### 4.- Activar el Nuevo Entorno.

Activa el entorno que acabas de crear para que las instalaciones se realicen dentro de él.

conda activate nuevo_entorno

Verás (nuevo_entorno) al inicio de la línea de comandos, confirmando que está activo.

### 5.- Instalar las Dependencias.

Ahora, usa el archivo requirements.txt que está en tu repositorio para instalar todos los paquetes que el proyecto necesita.

pip install -r requirements.txt

### 6.- Verificación.

Para asegurarte de que todos los paquetes se instalaron correctamente, puedes listar el contenido del nuevo entorno.

conda list

Con esto, tu proyecto estará completamente configurado y listo para correr en la nueva computadora, con exactamente las mismas librerías que tenías antes.
