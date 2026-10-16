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

## Region of Interest



### Preparación de la grabación

