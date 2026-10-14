# Precurso para el curso de iniciacion
Para poder aprovechar al máximo las sesiones presenciales, es fundamental realizar una preparación previa. El material precurso es **obligatorio** para todos los participantes. 

Se les enviará un ejercicio preparatorio sobre este tema la semana anterior al inicio del curso, para que lo completen y lo envíen a los instructores.

## Vídeo: Introducción a las bioimágenes
Antes de iniciar el curso, es fundamental hablar el mismo idioma en cuanto a los términos propios de la disciplina. Te recomendamos dedicar un tiempo a estudiar la introducción y el glosario de términos esenciales de análisis de bioimágenes (píxeles, bits, dimensiones, formatos de archivo, etc.). A continuación encontrarás una clase de imagen digital dictada en el Curso de Fundamentos de Microscopía Óptica y de FLuorescencia de 2026 donde se abordan estos temas. 

[Digitalización de la imagen](https://www.youtube.com/watch?v=FPcSHpwuAYc)

## Descargar FIJI
Fiji es una distribución de ImageJ preconfigurada con una amplia colección de plugins. Se distribuye como una versión portable (no requiere instalación formal, solo descomprimir). Descarga la versión adecuada para tu sistema operativo desde la página de descargas de Fiji.

[Página Fiji](https://imagej.net/software/fiji/downloads)

## Completar los ejercicios sobre conceptos básicos de FIJI 
Sigue los ejercicios que aparecen a continuación para familiarizarse con la apertura y manipulación de imágenes, así como con la ejecución de funciones básicas en ellas utilizando FIJI.

---

# Conceptos Básicos de FIJI

## Tabla de contenido
- [Qué es FIJI?](#Qué-es-fiji)
- [Primeros pasos con FIJI](#Primeros)
- [Abrir y ver imágenes](#abrir-ver)
- [Fonciones fundamental en Fiji](fonciones)

---

## Qué es FIJI?

**Fiji** (Fiji Is Just ImageJ) es una plataforma gratuita de código abierto para el procesamiento y análisis de imágenes, desarrollada sobre la base de ImageJ. Se utiliza ampliamente en la investigación científica, especialmente en microscopía, imagenología médica y análisis general de imágenes.

### Características clave
- **GUI fácil de usar** - No se requiere programación para operaciones básicas
- **Plugins pre-instalados** - Viene con una selecciń seleccionada de herramientas de procesamiento de imágenes
- **Ampliable** - Premite añadir complementos adicionales para tareas especializadas
- **Compatibilidad con múltiples formatos** - admite TIFF, JPEG, PNG, BMP y numerosos formatos cientificos
- **Batch processing** - Automatiza flujos de trabajo
- **Comunidad activa** - Amplia documentación y soporte en foros

### Casos de uso comunes
- Análisis de imágenes de microscopía
- Segmentación y thresholding
- Mediciones de intensidad
- registro y ensamblaje de imágenes
- Visualización de imágenes en 3D
- Análisis de series temporales

---

## Primeros pasos con Fiji

### Descarga e instalación

#### Windows, Mac, or Linux

1. Visita el sitio web oficial de Fiji: https://fiji.sc/
2. Haz clic en **"Download"** y seleccina tu sistema operativo.
3. Extrae el archivo descargado en la ubicación que prefieras (preferiblemente en un lugar donde no se requieran permisos de administrador para modificar archivos)
4. Haz doble clic en `Fiji.exe` (Windows) o en el paquete de la aplicación Fiji para iniciarla.

**No se requiere instalación adicional** - Fiji es una aplicación portátil e incluye java integrado.

#### Verificar la instalación

Al inicar Fiji, debería ver:
- La ventana principal de ImageJ (barra de herramientas con diversas funciones)
- Una barra de menús con **File**, **Edit**, **Image**, **Process**, **Analyze**, **Plugins**, **Window**, **Help**

<img width="1060" height="166" alt="Precurso-1" src="https://github.com/user-attachments/assets/0397db79-3d2e-45c8-98d5-ac29fffe0d30" />

### Preparación de los datos de muestra

Para este taller, recomendamos tener dispobibles imágenes de muestra. para el material previo al curso, por favor descargue la siguiente imagen:

[precurso_rinon.tif](https://drive.google.com/file/d/1BRXXbFWyGyUZZkwqZHouyBJlWdSQGHdQ/view?usp=drive_link)

_NB necisitará una cuenta de Google para acceder a esta imagen. por favor, eníenos un correo si tiene algún problema para descargarla_
---

## Abrir y visualizar imágenes

### Abrir una imagen

La forma más sencilla es arrastrar y soltar el archivo en el área gris.

Otra opciôn es:

1. **File → Open** (o `Ctrl+O` / `Cmd+O`)
2. Buscar el archivo de imagen y seleccionarlo
3. Hacer clic en **Open**

La imagen se mostrará en una nueva ventana con el nombre del archivo en la barra de título.

<div style="border: 2px solid gray; padding: 10px; background-color: #f9f9f9;">

>**EJERCICIO**
  
>Abrir precurso_planta.ome.tiff (that you previously downloaded) utlizando el importador BioFormats para generar las opciones de importación de  Bio-Formats Import Options (véase la imagen a continuacion):
>**Plugins → BioFormats → BioFormats Importer**

>_NB Este plugin de BioFormats también suele invocarse automáticamente para abrir la imagen._

<img width="1253" height="761" alt="Precurso-2" src="https://github.com/user-attachments/assets/29fba653-9726-4dee-8791-fff09639532f" />

>Lea la información relativa a cada una de las opciones (recuadro gris a la derecha). 
>Haz una lista de las opciones que no entiendas.
>

### Herramientas básicas de visualización

| Herramienta | Función | Shortcut |
|------|----------|----------|
| **Acercar/Alejar** <img width="51" height="45" alt="Precurso-zoom" src="https://github.com/user-attachments/assets/a1469090-97e6-4c75-b5a7-57256e473814" /> | Ajuste la ampliación para examinar detalles o ver la imagen completa | `+` / `-` o scroll |
| **Desplazar** <img width="51" height="45" alt="precurso-pan" src="https://github.com/user-attachments/assets/669ab164-2781-440f-9782-84c78b9a211d" />| Desplázase por la imagen cuando esté ampliada | Haz clic y arrastra con la barra espaciadora |
| **Medir** <img width="100" height="51" alt="precurso-measure" src="https://github.com/user-attachments/assets/e639b299-011f-4fa5-ae3f-c22e65a520bd" /> | Determine distancias y áreas | `M` |
| **ROI (Region of Interest)**<img width="202" height="51" alt="precurso-roi" src="https://github.com/user-attachments/assets/84752fbc-7fc2-4b20-b106-11b18cf4d99a" />  | Seleccione áreas rectangulares, ovaladas o de forma libre | Botones de la barra de herramientas |

> EJERCICIO  

>Haz tanto zoom como pueda en una región pequeña. ¿Qué ve?
>
>Si pasas el ratón sobre algunos píxeles, ¿qué ve en el área gris inferior de la ventana principal de FIJI?
>
>Mueve el cursor a la parte más brillante que encuentres en la imagen ampliada. ¿Cuál es el valor asociado a este píxel? Repite el procedimiento con el píxel más oscuro.


### Propiedades de una imagen

Tras abrir una imagen, primero revisa su encabezado. ¿Cuáles son los valores que aparecen en la parte superior?

¿Qué metadatos incluye? (`Image>Show Info...`)

<img width="642" height="543" alt="Precurso-3" src="https://github.com/user-attachments/assets/0ae72bdd-6aed-402e-a8ee-785d3c3d5113" />

>EJERCICIO
>
>Completa la siguiente tabla:
>
| Metadata artículo | Valor |
|---|---|
| Pixel Size (µm) | |
| Objective lens Magnification | |
| objective lens Numerical Aperture (NA) | |
| Bit Depth | |
| Image Dimensions (width × height) | |
| Number of Channels | |
| Number of Slices (if z-stack) | |
| Voxel Dimensions | |
| Unit | |

### Cambio de la profundidad de bits

Las imágenes pueden almacenarse en diferentes formatos que representan distintos niveles de información de intensidad:

- **8-bit** (256 niveles de intensidad) - mayor detalle, tamaño de archivo mayor, común en microscopía
- **16-bit** (65,536 niveles de intensidad) - mayor detalle, tamaño de archivo mayor, común en microscopía
- **32-bit** (floating-point) - Máxima precisión, tamaño de archivo mayor, utilizado para cálculos

Para cambiar la profundidad de bits de la imagen:

1. Vaya a `Image > Type` 
2. Seleccione la profundidad de bits deseada: `8-bit`, `16-bit`, or `32-bit`
3. Si se realiza una conversión de una profundidad de bits mayor a una menor (por ejemplo, de 16 a 8 bits), es posible que se pierda información.

---

## Funciones esenciales de Fiji

### Duplicar una imagen

A menudo, las operaciones que desee realizar en la imagen modificarán los valores de intensidad de forma irreversible. Para evitar tener que volver a abrir la imagen y repetir todo el proceso si algo sale mal, es recomendable duplicar la imagen al principio.

> EJERCICIO
> 
> Vaya a `Image > Duplicate`.
> 
> Duplicar la imagen, con ambos canales

###  Recorta tu imagen
1. Utilice la herramienta de selección rectangular para definir la región
2. **Image → Crop**
3. Tu imagen se ha reducido al área seleccionada

### Ajustar el brillo y el contraste

1. `Image > Adjust > Brightness/Contrast...`
2. Arrastra los controles deslizantes para mejorar la visibilidad
3. Hacer clic **Auto** para el adjuste automático
4. Utilizar **Reset** para volver al estado original

<img width="217" height="407" alt="Precurso-4" src="https://github.com/user-attachments/assets/aa66118f-021a-4097-a5a6-e4bcbc0a5d57" />

Esta función se utiliza para hacer que las imágenes tenues sean más visibles para su análisis.

>EJERCICIO
>
>Cambia los valores mínimos y máximos de tus imágenes duplicadas.
>
>Haz clic **Apply**
>
>Qué pasa a los valores de los pixeles?


### Generating image histogram


#### Exercise

Why might you want to convert a 16-bit image to 8-bit? Consider factors like file size, processing speed, memory usage, and the type of analysis you plan to do. When would it be a bad idea?



### Cambiando el LUT (LookUp Table)

La mayoría de las cámaras o detectores utilizados en la obtención de imágenes por fluorescencia son monocromáticos y solo recopilan información sobre la intensidad de los fotones que captan, no sobre la longitud de onda. Esto significa que el color con el que se representan las imágenes es un color falso, a menudo basado en los filtros de excitación y emisión empleados para cada canal.

Vaya a `Image > LookUp Tables` o haz clic en el LUT botón, que se encuentra en la barra de herramientas de Fiji

>EJERCICIO
>
>Piensa en para qué podrían utilizarse algunas de las diferentes paletas de colores. Prueba, por ejemplo, con HiLo, cool y la de 16 colores.


### Trabajar con múltiples dimensiones

Abre precuroso_rinon.tif, o abre una de tus propias Z-stacks con más de un canal. 

<img width="388" height="712" alt="Precurso-5" src="https://github.com/user-attachments/assets/e2eba624-633a-4f13-8688-b2670b4ef022" />

Los controles deslizantes de la parte inferior permiten recorrer los diferentes canales, planos Z y puntos temporales.
Algunas de las imágenes de muestra ya incluyen lo que se denomina una composición, en la que los canales se muestran simultáneamente.

#### Dividir canales
1. `Image > Color > Split Channels`
2. Cada canal abre en una ventana distinta
3. Analizar o procesar canales de forma independiente

#### Combinar canales
1. `Image > Color > Merge Channels`
2. Seleccione las ventanas de origen para cada canal
3. Eligir colores para cada canal, y elige si quieres crear una imagen compuesta, abrir nueva ventana con los resultados, o ignorar LUT de origen

<img width="346" height="433" alt="Precurso-6" src="https://github.com/user-attachments/assets/bdd2edab-2b19-4d54-8f8e-6c7c0aec723c" />

#### Visualización de canales
1. Abrir su iamgen
2. Ajuste el brillo y el contraste para una mejor visualización.
3. Vaya a `Image > Color > Make Composite`

###  Intensity Histogram
1. Go to **Analyze → Histogram**
2. Click on `Log`

What can you say about the histogram? Is it skewed to the left or right? What is the meximum intensity and how does this relate to the bit-depth? Is 0 the the minimum intensity or which one?

<--!
The histogram tells a lot about the image. In microscopy, most pixels correspond to the background, so a histogram skewed to the right points to a dark field, probably fluorescence microscopy image, while a histogram skewed to the left means that bright pixels are abundant and is likely to come from bright field. A maximum intensity of 255 or lower means that the bit-depth was probably 8-bit, while higher values means that bit-depth was higher. The minimum intensity also tells us something about the offset used and the risk of underexposing the acquisition.
-->

