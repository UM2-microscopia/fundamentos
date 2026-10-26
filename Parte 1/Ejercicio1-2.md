# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.2: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Eliminar el fondo de un imagen
- realizar operaciones con imágenes
- crear un fondo
- realizar un filtrado básico de imágenes

Cuando visualizamos una muestra, la señal que estamos detectando es una mezcla entre el ruido (ruido de fondo o background) y la señal que queremos detectar. Para identificar las estructuras de interés, necesitamos tener un alto valor de señal vs ruido, también llamado Signal-to-Noise Ratio (SNR).  
Recuerde que se espera que el fondo de las imágenes tenga un valor mayor a 0, mientras que la señal no debe tener pixeles saturados. Si el valor de un pixel es 0 no tenemos información real, dado que no sabemos si es -3 o -500; lo mismo pasa con los pixeles que tienen valores máximos. La mayoría de los microscopios tienen opciones para visualizar los histogramas y detectar cuándo los valores de intensidad por pixel se encuentran bajo el límite de detección. También puede utilizar el LUT HiLo en Fiji. Asegúrese de capturar sus imágenes utilizando estas opciones para que su fondo tenga un valor mayor a 0. 

## Filtros de imágenes
