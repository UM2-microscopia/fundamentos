# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.4: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Trabajar con RoI
- Crear mascaras
- Medir cosas en otros canales

## Pixel size
En este ejercicio, comenzaremos a extraer información cuantitativa a partir de las imágenes. Antes de proceder, debemos verificar si FIJI ha reconocido correctamente el tamaño del píxel. Cuando se trabaja con archivos obtenidos mediante software propietario de fabricantes de microscopios consolidados (ZEISS o Leica, por ejemplo), es muy probable que dichos archivos incluyan metadatos que FIJI pueda leer fácilmente, de modo que el tamaño del píxel ya sea el correcto. Sin embargo, en el caso de sistemas de fabricación propia, equipos antiguos o sistemas adaptados que utilizan software de adquisición de código abierto (por ejemplo, Micro-Manager), es probable que debas indicar a FIJI cuál es el tamaño del píxel con el que estás trabajando. 

1. open Neuron

## Region of Interest



### Preparación de la grabación
1. Abrir una imagen (`File` → `Open Samples` → `neuron`)
2. Abre la función de grabación de macros (`Plugins` → `Macros` → `Record..`)
3. Puede cambiar la lenguaje del script, y cambiar el nombre del archivo. 
