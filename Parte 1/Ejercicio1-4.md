# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.4: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Calcular y cambiar el tamaño del pixel de una imagen 
- Trazar una línea y generar un perfil de línea
- Crear una región de interés
- Realizar mediciones sencillas mediante el gestor de regiones de interés (ROI manager)


## Tamaño del pixel
En este ejercicio, comenzaremos a extraer información cuantitativa a partir de las imágenes. Antes de proceder, debemos verificar si FIJI ha reconocido correctamente el tamaño del píxel. Cuando se trabaja con archivos obtenidos mediante software propietario de fabricantes de microscopios consolidados (ZEISS o Leica, por ejemplo), es muy probable que dichos archivos incluyan metadatos que FIJI pueda leer fácilmente, de modo que el tamaño del píxel ya sea el correcto. Sin embargo, en el caso de sistemas de fabricación propia, equipos antiguos o sistemas adaptados que utilizan software de adquisición de código abierto (por ejemplo, Micro-Manager), es probable que debas indicar a FIJI cuál es el tamaño del píxel con el que estás trabajando. Siempre es conveniente comprobar que estas cifras tengan sentido antes de realizar cualquier cálculo, por si se hubiera producido algún error al leer los metadatos.

1. Abrir la imagen Neuron (`File` → `Open Samples` → `neuron`)
2. En esta nueva ventana, puede ver que el tamaño se muestra tanto en micras como en píxeles.

<img width="645" height="191" alt="Ej14-1" src="https://github.com/user-attachments/assets/f26b62ee-361d-42fc-b11b-f5a83ebd34fc" />

Existen 2 formas sencillas de comprobar los valores xy asignados a cada píxel:
1. `Analyze` → `Set Scale`. Se abrirá una nueva ventana que le permitirá asignar una distancia conocida a un número específico de píxeles, así como definir la unidad de medida y la relación de aspecto de los píxeles. Si ha dibujado una línea en su imagen, la ventana mostrará automáticamente la longitud en píxeles de dicha línea.
2. `Image` → `Properties..`. Se muestran el número de canales, cortes y marcos temporales, así como las dimensiones xyz de los píxeles y las unidades que tienen asignadas actualmente. Todos estos parámetros pueden modificarse aquí.

>EJERCICIO
>
>Abrir 'NoScale.tif' de la carpeta Precurso.
>Comprueba el tamaño del píxel en las propiedades de la imagen.
>
>La siguiente fórmula se utiliza para calcular el tamaño del píxel:
>
>     Image pixel size (um) = camera pixel size (um) / magnification 
>
>Sabe que el tamaño de píxel de su cámara es 5.3um, y la imagen sse adquirió utilizando un objecetivo 40X.
>
>Calcula el tamaño en píxeles de esta imagen y asígnalo a la imagen utilizando uno de los métodos descritos anteriormente.

## Mediciones de líneas simples

### Creación de un perfil de línea
Un perfil de línea nos indica los valores de intensidad de cada uno de los píxeles situados a lo largo de una línea. Esto resulta útil para visualizar el contenido de nuestras imágenes, comparar visualmente las intensidades en distintas zonas de una imagen o realizar estimaciones manuales del tamaño de un objeto, empleando parámetros como la FWHM (anchura a media altura).

1. Abrir la imagen Neuron (`File` → `Open Samples` → `neuron`)
2. Duplicar canal 4 (cyan)
3. Haz clic en el botón de «línea recta» en la barra de herramientas de FIJI
4. Traza una línea a través de un objeto de tu interés
5. `Analyse` → `Plot Profile` abre una nueva ventana en la que los valores de intensidad se representan en función de la distancia a lo largo de la línea
6. Al hacer clic en el botón `Live` situado en la parte inferior derecha, se vincula de forma dinámica la línea trazada en la imagen con el gráfico; al desplazar dicha línea, el gráfico se actualizará automáticamente para mostrar el nuevo perfil.
7. Los datos del perfil se pueden guardar: `Data` -> `Save Data...`, o se pueden copiar para pegar en excel: `Data` -> `Copy 1st Data Set` 
8. La línea recta puede modificarse haciendo clic con el botón derecho en el botón de línea para mostrar formatos de línea alternativos (esto es posible con cualquier icono que presente un triángulo rojo orientado hacia abajo).

<img width="1065" height="258" alt="Ej14-2" src="https://github.com/user-attachments/assets/6c441048-c80e-4189-8e78-b2cd6c30e15a" />


>EJERCICIO
>
>Dibuja una línea y haz clic en «list» (lista). ¿Qué se muestra?
>Modifica las propiedades del gráfico experimentando con el botón `More>>`.
>Cambia el perfil de línea a `Freehand Line` (línea a mano alzada), dibuja una forma y genera un perfil de línea.
>¿Qué problemas de reproducibilidad podrían surgir al utilizar estas herramientas?
>Prueba a abrir la imagen de la neurona con los 5 canales, traza una línea, genera un perfil y configúralo en modo en `live`). Alterna entre los >canales y observa qué sucede.

### Medir longitud

1. Vuelve a la imagen del canal 4 de la neurona y amplía la región de los núcleos utilizando el botón de la lupa en la barra de herramientas principal de FIJI.
2. Cambia la LUT a «HiLo» para visualizar mejor el contraste.
3. Dibuja una línea recta a lo largo del diámetro del núcleo situado en el centro de la imagen, observando la barra de herramientas principal de FIJI mientras lo haces.
4. Deberías ver la longitud de la línea, así como el ángulo respecto a la posición inicial y las coordenadas de la línea.

<img width="1056" height="642" alt="Ej14-3" src="https://github.com/user-attachments/assets/c83401c8-ef1a-4e6f-a586-5460c6281584" />

Este método para medir la longitud de un objeto resulta útil para una consulta rápida, pero no es adecuado para realizar mediciones precisas; sobre todo porque el valor desaparece en cuanto se aleja el puntero del ratón del punto final de la línea, y no vuelve a aparecer.

To save a measurement of the line, 


## Region of Interest





