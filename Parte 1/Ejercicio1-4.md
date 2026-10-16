# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.4: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Trabajar con RoI
- Crear mascaras
- Medir cosas en otros canales

## Pixel size
En este ejercicio, comenzaremos a extraer información cuantitativa a partir de las imágenes. Antes de proceder, debemos verificar si FIJI ha reconocido correctamente el tamaño del píxel. Cuando se trabaja con archivos obtenidos mediante software propietario de fabricantes de microscopios consolidados (ZEISS o Leica, por ejemplo), es muy probable que dichos archivos incluyan metadatos que FIJI pueda leer fácilmente, de modo que el tamaño del píxel ya sea el correcto. Sin embargo, en el caso de sistemas de fabricación propia, equipos antiguos o sistemas adaptados que utilizan software de adquisición de código abierto (por ejemplo, Micro-Manager), es probable que debas indicar a FIJI cuál es el tamaño del píxel con el que estás trabajando. 

1. Abrir la imagen Neuron (`File` → `Open Samples` → `neuron`)
2. En esta nueva ventana, puede ver que el tamaño se muestra tanto en micras como en píxeles.

<img width="645" height="191" alt="Ej14-1" src="https://github.com/user-attachments/assets/f26b62ee-361d-42fc-b11b-f5a83ebd34fc" />

Existen 2 formas sencillas de comprobar los valores xy asignados a cada píxel:
1. `Analyze` → `Set Scale`. Se abrirá una nueva ventana que le permitirá asignar una distancia conocida a un número específico de píxeles, así como definir la unidad de medida y la relación de aspecto de los píxeles. Si ha dibujado una línea en su imagen, la ventana mostrará automáticamente la longitud en píxeles de dicha línea.
2. `Image` → `Properties..`. Se muestran el número de canales, cortes y marcos temporales, así como las dimensiones xyz de los píxeles y las unidades que tienen asignadas actualmente. Todos estos parámetros pueden modificarse aquí.

>EJERCICIO
>
>Open an image that hasn't get any values assigned to it
>you know that the pixel size of your camera is XXXum.
>Check the metadata for the image to determine which Objective lens was used to acquire this image
The pixel size can be calculated using the following formula:
     image pixel size = camera pixel size (um) / magnification 
>Calculate the pixel size for this image and assign it to the image using one of the methods outlined above. 

## Region of Interest



### Preparación de la grabación

