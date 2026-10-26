# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.2: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Eliminar el fondo de un imagen
- realizar operaciones con imágenes
- crear un fondo
- realizar un filtrado básico de imágenes

Cuando visualizamos una muestra, la señal que estamos detectando es una mezcla entre el ruido (ruido de fondo o background) y la señal que queremos detectar. Para identificar las estructuras de interés, necesitamos tener un alto valor de señal vs ruido, también llamado Signal-to-Noise Ratio (SNR).  
Recuerde que se espera que el fondo de las imágenes tenga un valor mayor a 0, mientras que la señal no debe tener pixeles saturados. Si el valor de un pixel es 0 no tenemos información real, dado que no sabemos si es -3 o -500; lo mismo pasa con los pixeles que tienen valores máximos. La mayoría de los microscopios tienen opciones para visualizar los histogramas y detectar cuándo los valores de intensidad por pixel se encuentran bajo el límite de detección. También puede utilizar el LUT HiLo en Fiji. Asegúrese de capturar sus imágenes utilizando estas opciones para que su fondo tenga un valor mayor a 0. 

1. En Fiji `File` → `Open Samples` → `HeLa Cells (48-bit RGB)`
2. Luego `Image` → `Color` → `Split Channels`
3. Selecciona la imagen C2 (Canal 2, verde), puedes cerrar las otras dos imágenes.
4. Cambia el LUT de la imagen a escala de grises 

Para cada ejercicio duplique la imagen original y trabaje en la imagen duplicada 

## Caracterización y sustracción del Ruido de Fondo de la imagen (Fondo Constante)

Una forma sencilla de caracterizar el ruido de fondo de la imagen es obtener la intensidad promedio de una región de la imagen sin muestra (en este caso una región que no contenga ninguna célula). Luego el valor de intensidad de fondo se resta a toda la imagen. 

Nota: si la muestra no tuviera una región de fondo (como podría pasar en la imagen de una monocapa celular o de un tejido) se puede usar el algoritmo de Rolling Ball mencionado en el siguiente punto. para corregir iluminación no uniforme. 

>EJERCICIO
>
>Cambie los bits de la imagen a 32 bits

Reforzar; 

Las imágenes de 16 bits poseen un rango dinámico de **0 a 65,535 niveles de gris**. A diferencia de los formatos de punto flotante (32 bits), los números enteros de 16 bits **no admiten valores negativos**. Si al restar el ruido el resultado de un píxel es menor que 0, el software lo convertirá automáticamente en 0, perdiendo información cuantitativa.  Este fenómeno se conoce como *clipping* o truncamiento. 

Si no se pasa la imagen a 32bit, al realizar la resta del fondo a todos los píxeles de la imagen, los píxeles que contengan valores negativos serán considerados con valor 0 (notar que las escalas 8 bit y 16 bit admiten enteros positivos\!). 

* Seleccione la herramienta **Rectangle** u **Oval**. 

* Dibuje una región de interés (**ROI**) en una zona de `imagen_celula.tif` donde **no haya células**. 

* Presione **Ctrl \+ M** (**Analyze \> Measure**). Anote el valor de la intensidad promedio (**Mean**). 

* Mueva el ROI a otras 3 regiones vacías y repita la medición (**Ctrl \+ M**). Si los valores de **Mean** son muy similares entre sí, el fondo es constante y se resta el valor escalar a todos los píxeles de la imagen. (Si la intensidad de fondo varía, es preferible usar el método Rolling Ball de la sección siguiente) 

* Vaya a **Process \> Math \> Subtract…  .** Introduzca el valor promedio de la intensidad de fondo. Haga clic en **OK**. *(Nota: Como su imagen es de 32 bits gracias al paso 5, no hay riesgo de truncamiento en los píxeles)*. 

Guarde la imagen para comparar posteriormente 


## Sustracción de Fondos Variables: **Algoritmo Rolling Ball** 

Cuando la señal de fondo no es constante en la imagen o la iluminación no es uniforme, restar un único valor numérico no es la mejor opción. En estos casos podemos usar el algoritmo de "bola rodante" (*Rolling Ball*). 

 Duplique la imagen original 

* Vaya a **Process \> Subtract Background...**   
* Configure los siguientes parámetros clave:

ADD IN THE OTHER IMAGE HERE


* **Rolling ball radius:** Define el radio de una esfera virtual que rueda bajo el mapa de relieve de la imagen. Debe ser **mayor** que el diámetro del objeto de interés más grande del campo de visión (por ejemplo, si la célula mide 60 píxeles de diámetro, configure un radio de 80 píxeles).   

  Con la herramienta **Straight Line** (Línea) se puede medir el diámetro o ancho del objeto más grande de tu imagen (por ejemplo, una célula o un cúmulo). El valor del radio debe ser al menos tan grande como ese objeto.    

* **Light background:** marcarlo si tu imagen tiene un fondo brillante (blanco o claro) y objetos oscuros. Dejarlo desmarcado si el fondo es oscuro y las señales/objetos son brillantes.   

* **Create background (don't subtract):** Si se activa, muestra la matriz del fondo calculado en lugar de restarlo. Es muy didáctico para verificar qué está interpretando el software como "ruido".   

* **Sliding paraboloid:** Cambia la esfera perfecta por una forma de paraboloide. Trata los bordes de forma más suave y reduce la aparición de líneas o artefactos extraños en los límites de los objetos.   

* **Disable smoothing:** Evita que el software aplique un filtro de suavizado inicial (promedio de 3x3 píxeles) antes de calcular el fondo. Se desmarca por defecto para reducir el ruido.   

* Active la casilla **Preview** para comprobar el resultado en tiempo real y presione **OK**. 

Compare con la imagen anterior. 




