# Instalación y uso de Python con entornos

Es habitual que los proyectos desarrollados en Python utilicen un gran número de librerías externas. En muchos casos varios proyectos utilizan diferentes versiones de la misma librería, e incluso distintas versiones de Python.

Por ello, y para evitar conflictos y problemas, se recomienda instalar Python usando [Conda](https://conda.io/projects/conda/en/latest/index.html), un sistema para instalar y manejar las diferentes versiones de Python y sus librerías en cualquier sistema operativo.

### Instalación
1. Descargar e instalar Conda (se recomienda usar el instalador de **Miniconda**). En el enlace a continuación podéis encontrar los instaladores para [Linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html), [Windows](https://docs.conda.io/projects/conda/en/latest/user-guide/install/windows.html) y [macOS](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html).

	[https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links)
    

2. Abrir una terminal (o el *Anaconda Prompt* en Windows) y comprobar que se ha instalado **Miniconda** correctamente con el comando:
	
	```
	conda --version
	```

3. En la misma terminal de antes, crear un entorno de Conda para usar durante la hackatón, por ejemplo llamado *braincodegamesenv*:

	```
	conda create --name braincodegamesenv
	```

4. Activar el entorno que acabamos de crear (hay que hacerlo cada vez que se abre una terminal):

	```
	conda activate braincodegamesenv
	```

5. Instalar la librería *pip*, que nos permitirá instalar los paquetes y librerías que necesitemos:

	```
	conda install pip
	```

<br>
### Uso de un entorno
A partir de ahora debemos activar nuestro entorno cada vez que queramos usarlo. Para ello hay que ejecutar el comando del paso 4. Por lo demás, podemos instalar paquetes y usar Python de la misma manera que se haría sin un entorno.

Si, por ejemplo, quisiesemos instalar la librería *numpy* en su última versión, lo haríamos con:

```
pip install numpy
```

Si necesitasemos en concreto la versión 1.18.1 de *numpy*, podemos instalarla usando:

```
pip install numpy=1.18.1
```

Así podemos mantener nuestro entorno controlado y limpio para evitar errores y conflictos entre versiones.


<br>
### Exportar y compartir entornos
Conda también nos permite exportar e importar entornos, lo cual es muy útil cuando se trabaja en grupo ya que permite compartir un mismo entorno. Para exportar un entorno se usa el comando:

```
conda braincodegamesenv export > environment.yml
```

Esto guardaría nuestro entorno braincodegamesenv en el fichero environment.yml, que contendrá la información de todas las librerías y paquetes que estemos utilizando. Otro usuario puede ahora crear su entorno usando este fichero haciendo:

```
conda env create -n braincodegamesenv -f environment.yml
```

De esta manera el nuevo entorno se habrá creado con las mismas librerías (y en la misma versión) que las del entorno original.