# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.1: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Utilizar Fiji recorder para documentar los procesos del taller
- Entender y aprender a utilizar histogramas
- Modificar brillo y contraste
- Utilizar distintos LUTs para visualizar la imagen


## Registrar procesos en FIJI

Un aspecto fundamental de lo que buscamos al realizar análisis de imágenes es garantizar que nuestros flujos de trabajo sean reproducibles; es decir, que puedan ser replicados tanto por nosotros mismos en todo nuestro conjunto de datos como por cualquier otra persona en el futuro. Conocer los pasos de procesamiento seguidos nos permite evaluar de manera crítica si podemos confiar en la solidez de nuestros resultados.

Una herramienta útil para lograr esto es la función «Record Macro» (grabar macro), disponible en FIJI. Esta herramienta no solo facilita la creación de macros, sino que también registra cada proceso que aplicamos a nuestras imágenes. Posteriormente, este registro puede exportarse y guardarse junto con los datos, permitiéndonos saber exactamente cómo han sido procesados.

### Preparación de la grabación
1. Abrir una imagen (`File` → `Open Samples` → `neuron`)
2. Abre la función de grabación de macros (`Plugins` → `Macros` → `Record..`)
3. Puede cambiar la lenguaje del script, y cambiar el nombre del archivo. 

<img width="906" height="477" alt="E1-1_1" src="https://github.com/user-attachments/assets/37e21419-a36a-40d9-8d08-ace3f7fdcddb" />

>EJECICIO
>
>Observa la ventana de 'Recorder' mientras realizas los siguientes procesos que se abordaron en el material previo al curso:
>1. Duplica la imagen
>2. separa los canales en imágenes independientes
>3. selecciona el canal azul y cambia la profundidad de bits a 8 bits
>4. selecciona el canal verde y cambia la LUT
>5. vuelve a combinar los canales verde y rojo
>   
>¿Qué procesos está registrando y cuáles no está registrando? ¿En qué punto de tu flujo de trabajo de procesamiento de imágenes podría interesarte grabar una macro?

### Guardando tus procesos

Para guardar tus procesos, haz clic en el botón `Create` en la barra de herramientas de la ventana `Recorder`. Esto generará un archivo *.ijm que contendrá todos tus procesos traducidos al lenguaje de macros de FIJI.

<img width="875" height="790" alt="E1-1_2" src="https://github.com/user-attachments/assets/718a79be-b3f9-4b08-a962-278e0f2314c9" />

Esto puede guardarse en este formato, o bien puedes utilizar este script para ejecutar los mismos procesos en cualquier imagen posterior que abras.

>EJERCICIO
>
>1. Cierra todas las ventanas de imagen que tuvieras abiertas y vuelve a abrir la imagen de la neurona.
>2. Haz clic en `Run` en tu macro, dentro de la ventana `*.ijm`.
>3. ¿Qué limitaciones observas al ejecutar macros de esta manera?

## Histogramas & visualización de características
Encontramos histogramas en el precurso. 

Para el análisis de bioimágenes es fundamental distinguir qué operaciones modifican los valores de intensidad de los píxeles de aquellas que solo alteran su visualización. En esta sección aprendimos como utilizar las herramientas de contraste de forma segura.

### Visualización de la imágen
1. Abrir la imágen M51.tif (`File` → `Open Samples` → `M51`)
2. Inspeccionar su histograma (`Analyze` → `Histogram`)

>¿Qué se ve en la imagen?

3. Duplicar la imagén (`Image` → `Duplicate`), y dibujar una línea en la imagen y ver el perfil de intensidades (`Analyze` > `Plot profile`). Habilitar la opción `Live` del Plot profile y mover la línea para analizar diferentes partes de la imagen.
4. Manipular el brillo y contraste (`Image` > `Adjust` > `Brightness/Contrast...`) de la visualización de la imagen para descubrir regiones no visibles de la imagen y elegir la «mejor imagen» a su criterio.
Aparecerá una ventana emergente que le permitirá establecer los valores mínimo y máximo de gris, el brillo y el contraste. La opción `Auto` le proporcionará los ajustes que el software considera óptimos; aplica un contraste inteligente.
>EJERCICIO
>¿Qué se muestra en la región superior del cuadro de diálogo de B&C?
>
>La operación que se realiza es una transformación lineal representada por la recta que se muestra. Cuando se mueven los parámetros (minimum, maximum, brightness, contrast) se mueve la línea. Puede hacerlo para cada canal. ¿Qué representan estos parámetros de la transformación lineal?

5. Si el botón `Auto` no produce un resultado deseable, utilice la herramienta de región de interés (ROI) para seleccionar una parte de la célula y algo de fondo, y haga clic en `Auto`. El ajuste de rango (stretch) se basará entonces en las intensidades de dicha región de interés.
>Dibuja una forma y muévela por la imagen, pulsando «auto» en distintos puntos. ¿Cómo cambia la imagen?
>
>Pulsa «Reset» para mostrar la imagen tal como apareció inicialmente.
>¿Esto sugiere que hemos modificado de forma permanente los valores de los píxeles, o que simplemente hemos cambiado su apariencia?

6. El rango de visualización puede ajustarse manualmente mediante el botón `Set` y aplicarse a otras imágenes que tenga abiertas.
>Duplicar la imagen, y cambiar el max y min para una de las dos.
>Haz clic `Set` en una, y elige `Propaagate to all other open channels`.
> Hacer clic `reset`. ¿Que pasa?

7. Al pulsar el botón `Apply`, se modifican de forma permanente los valores de gris reales de la imagen. 
>Duplicar la imagen, y comparar los histogramas de una imagen a la cual se le manipuló el brillo y contraste SIN poner APPLY con el de la misma imagen pero poniendo APPLY.
Si está analizando la intensidad de la imagen, no pulse este botón.

### Mejorar el contraste de la imagen

La función de contraste mejorado (Enhance Contrast) en FIJI mejora el contraste de la imagen ajustando la distribución de las intensidades de los píxeles, con el fin de hacer que los objetos presentes en la imagen sean más distinguibles.

1. Duplicar la imagen original y aplicar Enhance contrast (`Process` → `Enhance contrast` (sin las opciones Normalize ni Equalize). Varíe el porcentaje de píxeles saturados (típicamente se usa 0.3% o 0.4%).

Este número define el porcentaje de píxeles atípicos a los que se permite alcanzar la saturación total (recortados a blanco o negro). Un valor como 0,35 evita que unos pocos valores extremos arruinen el ajuste del histograma. Aumentar este número incrementa el contraste.

>¿Qué arriesgas al aumentar este número?

2. Duplicar la imagen original y aplicar la normalización a la imagen original (`Process` → `Enhance contrast` → `Normalize`). Esto recalcula los valores de los píxeles de modo que todo el rango se ajuste al intervalo máximo posible para el tipo de imagen (por ejemplo, 0-255 para 8 bits, etc.).
3. Duplicar la imagen original y aplicar la ecualización de histograma a la imagen original(`Process` → `Enhance contrast` → `Equalize`). Esta función transforma el histograma de la imagen de modo que los niveles de intensidad queden distribuidos de manera más uniforme a lo largo del rango dinámico. 

>Comparar los histogramas de la imagen original y las imágenes obtenidas en las partes 3, 4, 5 y 6.
>¿Cuál de los procedimientos anteriores (3, 4, 5 y 6) es reproducible?


## Utilizando LUTs como control de calidad y rango dinámico 
Tablas de consulta (Look Up Tables, LUTs) are the colour given to a specific range 

(Identificación de Píxeles Saturados y Sin Señal)

En esta práctica, utilizaremos tablas de consulta (LUTs) e histogramas para identificar problemas críticos de exposición como la saturación y la subexposición,  asegurando que las imágenes sean válidas para su posterior análisis.
Atención: la presencia de píxeles con valores saturados o nulos es un defecto que no se puede corregir mediante el análisis de imágenes. 

Se propone usar las imágenes publicadas en https://zenodo.org/records/15374754
Descargar las imágenes: 
sequential.nd2:  imagen de dos canales obtenida en forma secuencial y en condiciones óptimas que llamaremos muestra_optima
seq_underexposed.nd2  que llamaremos muestra_subexpuesta
seq_saturated.nd2        muestra_saturada

Paso 1: Documentar procesos



Paso 1: Inspección visual de los valores de intensidad de la imagen mediante LUT
Abre las tres imágenes de prueba en Fiji (por ejemplo: muestra_subexpuesta.tif, muestra_saturada.tif y muestra_optima.tif).
Para cada una de las imágenes, ve a Image > Lookup Tables y selecciona HiLo.
La tabla de color (LUT) HiLo mostrará la imagen en escala de grises, pero pintará automáticamente de azul los píxeles que valgan exactamente 0 (sin señal) y de rojo puro los píxeles que alcancen el valor máximo del rango dinámico (saturados). 
Observar las 3 imágenes en la escala HiLo y evaluar la presencia de píxeles sin señal o saturados. 
Comentario: Además, el LUT HiLo, es muy útil para ajustar el contraste en forma precisa. Permite cambiar los valores de brillo y contraste sin saturar la imagen por accidente. 
Como sugerencia ajuste en forma manual el brillo y contraste (pruebe cambiar valor mínimo y máximo, brillo y contraste)  de la imagen  muestra_optima.tif empleando el LUT HiLO.

Paso 2: Evaluación mediante el histograma de intensidad de los píxeles de una imagen. 
El histograma es la herramienta gráfica fundamental para realizar el control de calidad de una imagen científica. Permite diagnosticar de un vistazo la exposición, el rango dinámico y la validez de los datos antes de realizar cualquier análisis. 
Haz clic en la primera imagen (muestra_optima.tif) y presiona Ctrl + H (o ve a Analyze > Histogram). Este paso te permitirá observar el histograma de la intensidad de todos los píxeles de la imagen. Notar que entre otra información, podemos ver el valor mínimo y el máximo de intensidad.
Repetir el proceso con la imagen subexpuesta (muestra_subexpuesta.tif) y  la imagen saturada (muestra_saturada.tif).
Observar cada histograma y compararlos, en particular prestar atención a sus valores extremos. 
Si el histograma presenta píxeles con intensidad 0, significa que se ha perdido la información de esos píxeles por falta de señal. Por otro lado, si existen píxeles con el valor máximo de la escala según la profundidad de bits (por ejemplo, 255 en 8 bits o 65 535 en 16 bits), entonces esas zonas están saturadas y tampoco ofrecen información cuantitativa confiable.  



PARTE 2 -Manejo de brillo, contraste y ecualización de histograma

Para el análisis de bioimágenes es fundamental distinguir qué operaciones modifican los valores de intensidad de los píxeles de aquellas que solo alteran su visualización. El siguiente ejercicio está pensado para utilizar las herramientas de contraste de forma segura.
Abrir la imágen M51.tif de ImageJ/Fiji. 
File  > Open Samples buscar la imagen  M51.tif 
¿Qué se ve en la imagen? Inspeccionar su histograma (Analyze > Histogram ).
 Duplicar la imagen  (Image > Duplicate ).
Dibujar una línea en la imagen y ver el perfil de intensidades (Analyze > Plot profile). Habilitar la opción «Live» del Plot profile y mover la línea para analizar diferentes partes de la imagen.
Manipular el brillo y contraste (Image > Adjust > Brightness/Contrast...) de la visualización de la imagen para descubrir regiones no visibles de la imagen y elegir la «mejor imagen» a su criterio.
¿Qué se muestra en la región superior del cuadro de diálogo de B&C?
La operación que se realiza es una transformación lineal representada por la recta que se muestra. Cuando se mueven los parámetros (minimum, maximum, brightness, contrast) se mueve la línea. ¿Qué representan estos parámetros de la transformación lineal?
Duplicar la imagen original y aplicar Enhance contrast (Process > Enhance contrast (sin las opciones Normalize ni Equalize). Varíe el porcentaje de píxeles saturados (típicamente se usa 0.3% o 0.4%). 
Duplicar la imagen original y aplicar la normalización a la imagen original (Process > Enhance contrast  opción Normalize)
 Duplicar la imagen original y aplicar la ecualización de histograma a la imagen original(Process > Enhance contrast opción Equalize)
Comparar los histogramas de la imagen original y las imágenes obtenidas en las partes 3, 4,  5 y 6.
¿Cuál de los procedimientos anteriores (3, 4, 5 y 6) es reproducible?

Adicional:  Compare los histogramas de una imagen a la cual se le manipuló el brillo y contraste SIN poner APPLY con el de la misma imagen pero poniendo APPLY. 
