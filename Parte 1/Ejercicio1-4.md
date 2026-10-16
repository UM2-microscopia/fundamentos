# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.4: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Trabajar con RoI
- Crear mascaras
- Medir cosas en otros canales

## Pixel size
En este ejercicio, comenzaremos a extraer información cuantitativa a partir de las imágenes. Antes de proceder, debemos verificar si FIJI ha reconocido correctamente el tamaño del píxel. Cuando se trabaja con archivos obtenidos mediante software propietario de fabricantes de microscopios consolidados (ZEISS o Leica, por ejemplo), es muy probable que dichos archivos incluyan metadatos que FIJI pueda leer fácilmente, de modo que el tamaño del píxel ya sea el correcto. Sin embargo, en el caso de sistemas de fabricación propia, equipos antiguos o sistemas adaptados que utilizan software de adquisición de código abierto (por ejemplo, Micro-Manager), es probable que debas indicar a FIJI cuál es el tamaño del píxel con el que estás trabajando. 

1. Abrir la imagen Neuron (`File` → `Open Samples` → `neuron`)
2. In this new window, yu can see that there's a size show both in microns and in pixels.

<img width="645" height="191" alt="Ej14-1" src="https://github.com/user-attachments/assets/f26b62ee-361d-42fc-b11b-f5a83ebd34fc" />

There are 2 easy ways to check the xy values assigned to each pixel:
1. `Analyze` → `Set Scale`. A new window will open, allowoing you to assign a Known distance for a specific number of pixels, the unit of lenegth and the Pixel aspect ratio. You can also do this oon 
2. 

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

