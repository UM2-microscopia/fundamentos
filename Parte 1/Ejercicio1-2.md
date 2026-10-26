# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.2: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Eliminar el fondo de un imagen
- realizar operaciones con imágenes
- crear un fondo
- realizar un filtrado básico de imágenes

Cuando visualizamos una muestra, la señal que estamos detectando es una mezcla entre el ruido (ruido de fondo o background) y la señal que queremos detectar. Para identificar las estructuras de interés, necesitamos tener un alto valor de señal vs ruido, también llamado Signal-to-Noise Ratio (SNR).  
Recuerde que se espera que el fondo de las imágenes tenga un valor mayor a 0, mientras que la señal no debe tener pixeles saturados. Si el valor de un pixel es 0 no tenemos información real, dado que no sabemos si es -3 o -500; lo mismo pasa con los pixeles que tienen valores máximos. La mayoría de los microscopios tienen opciones para visualizar los histogramas y detectar cuándo los valores de intensidad por pixel se encuentran bajo el límite de detección. También puede utilizar el LUT HiLo en Fiji. Asegúrese de capturar sus imágenes utilizando estas opciones para que su fondo tenga un valor mayor a 0. 

## Caracterización y sustracción del Ruido de Fondo de la imagen (Fondo Constante)

Una forma sencilla de caracterizar el ruido de fondo de la imagen es obtener la intensidad promedio de una región de la imagen sin muestra (en este caso una región que no contenga ninguna célula). Luego el valor de intensidad de fondo se resta a toda la imagen. 

Nota: si la muestra no tuviera una región de fondo (como podría pasar en la imagen de una monocapa celular o de un tejido) se puede usar el algoritmo de Rolling Ball mencionado en el siguiente punto. para corregir iluminación no uniforme. 

En Fiji File - Open sample images - HeLa Cells (48-bit RGB) 

Luego Image – Color – Split Channels  

Selecciona la imagen C2 (Canal 2, verde), puedes cerrar las otras dos imágenes. 

Cambia el LUT de la imagen a escala de grises 

Para cada ejercicio duplique la imagen original y trabaje en la imagen duplicada 


