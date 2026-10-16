# Parte 1: Procesamiento y análisis de imágenes 2D

## Ejercicio 1.3: Objetivos de Aprendizaje

Al finalizar la sesión, los alumnos serán capaces de:

- Entender como utilizar filtros de imágenes
- Realizar cálculos en imágenes

## Filtros de imágenes

Un aspecto fundamental de lo que buscamos al realizar análisis de imágenes es garantizar que nuestros flujos de trabajo sean reproducibles; es decir, que puedan ser replicados tanto por nosotros mismos en todo nuestro conjunto de datos como por cualquier otra persona en el futuro. Conocer los pasos de procesamiento seguidos nos permite evaluar de manera crítica si podemos confiar en la solidez de nuestros resultados.

Una herramienta útil para lograr esto es la función «Record Macro» (grabar macro), disponible en FIJI. Esta herramienta no solo facilita la creación de macros, sino que también registra cada proceso que aplicamos a nuestras imágenes. Posteriormente, este registro puede exportarse y guardarse junto con los datos, permitiéndonos saber exactamente cómo han sido procesados.

### Preparación de la grabación
1. Abrir una imagen (`File` → `Open Samples` → `neuron`)
2. Abre la función de grabación de macros (`Plugins` → `Macros` → `Record..`)
3. Puede cambiar la lenguaje del script, y cambiar el nombre del archivo. 
