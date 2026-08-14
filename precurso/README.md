# Precurso para el curso de iniciacion
Para poder aprovechar al máximo las sesiones presenciales, es fundamental realizar una preparación previa. El material precurso es **obligatorio** para todos los participantes. 

Se les enviará un ejercicio preparatorio sobre este tema la semana anterior al inicio del curso, para que lo completen y lo envíen a los instructores.

## Vídeo: Introducción a las bioimágenes
Antes de iniciar el curso, es fundamental hablar el mismo idioma en cuanto a los términos propios de la disciplina. Te recomendamos dedicar un tiempo a estudiar la introducción y el glosario de términos esenciales de análisis de bioimágenes (píxeles, bits, dimensiones, formatos de archivo, etc.). A continuación encontrarás una clase de imagen digital dictada en el Curso de Fundamentos de Microscopía Óptica y de FLuorescencia de 2026 donde se abordan estos temas. 

[Digitalización de la imagen](https://www.youtube.com/watch?v=FPcSHpwuAYc)

## Download FIJI
Fiji es una distribución de ImageJ preconfigurada con una amplia colección de plugins. Se distribuye como una versión portable (no requiere instalación formal, solo descomprimir). Descarga la versión adecuada para tu sistema operativo desde la página de descargas de Fiji.

[Fiji download page](https://imagej.net/software/fiji/downloads)

---

# Conceptos Básicos de FIJI

## Table of Contents
- [Qué es FIJI?](#Qué-es-fiji)
- [Primeros pasos con FIJI](#Primeros)
- [Abrir y ver imágenes](#abrir-ver)
- [Fonciones fundamental en Fiji](fonciones)

---

## Qué es FIJI?

**Fiji** (Fiji Is Just ImageJ) is a free, open-source image processing and analysis platform built on top of ImageJ. It's widely used in scientific research, particularly in microscopy, medical imaging, and general image analysis.

### Key Features
- **User-friendly GUI** - No programming required for basic operations
- **Pre-installed plugins** - Comes with a curated selection of image processing tools
- **Extensible** - Can add additional plugins for specialized tasks
- **Multi-format support** - Handles TIFF, JPEG, PNG, BMP, and many scientific formats
- **Batch processing** - Automate workflows with macros
- **Active community** - Extensive documentation and forum support

### Common Use Cases
- Microscopy image analysis
- Segmentation and thresholding
- Intensity measurements and statistics
- Image registration and stitching
- 3D image visualization
- Time-series analysis

---

## Getting Started with Fiji

### Download and Installation

#### Windows, Mac, or Linux

1. Visit the official Fiji website: https://fiji.sc/
2. Click **"Download"** and select your operating system
3. Extract the downloaded file to your preferred location (preferably somewhere admin rights are not required to modify files)
4. Double-click `Fiji.exe` (Windows) or the Fiji application bundle to launch

**No additional installation required** - Fiji is portable and comes with Java bundled.

#### Verify Installation

When you launch Fiji, you should see:
- The main ImageJ window (toolbar with various tools)
- A menu bar with **File**, **Edit**, **Image**, **Process**, **Analyze**, **Plugins**, **Window**, **Help**

<img width="1060" height="166" alt="Precurso-1" src="https://github.com/user-attachments/assets/0397db79-3d2e-45c8-98d5-ac29fffe0d30" />

### Setting Up Sample Data

For this workshop, we recommend having sample images available. You can:

ADD OUR OWN DATA SUGGESTIONS HERE, THINK ABOUT WHAT WE NEED

---

## Opening and Viewing Images

### Opening an Image

The easiest way is to use drag-and-drop on the gray area.

Another option is to:

1. **File → Open** (or `Ctrl+O` / `Cmd+O`)
2. Navigate to your image file and select it
3. Click **Open**

The image will display in a new window with the filename in the title bar.

Open an image using the BioFormats importer in order to generate the Bio-Formats Import Options (see image below):
**Plugins → BioFormats → BioFormats Importer**

_NB This BioFormats Plugin is often also automatically called to open the image._

<img width="1253" height="761" alt="Precurso-2" src="https://github.com/user-attachments/assets/29fba653-9726-4dee-8791-fff09639532f" />

Read the 'Infomation' relating to each of the options (grey box on the righthand side). 
Make a list of any of the options that you don't understand. 

### Basic Viewing Tools

| Tool | Function | Shortcut |
|------|----------|----------|
| **Zoom In/Out** <img width="51" height="45" alt="Precurso-zoom" src="https://github.com/user-attachments/assets/a1469090-97e6-4c75-b5a7-57256e473814" /> | Adjust magnification to inspect details or see whole image | `+` / `-` or scroll wheel |
| **Pan** <img width="51" height="45" alt="precurso-pan" src="https://github.com/user-attachments/assets/669ab164-2781-440f-9782-84c78b9a211d" />| Move around the image when zoomed in | Click and drag with spacebar |
| **Measure** /home/charlotte/Documents/Microscope Facility/Image Analysis courses/Basico/Images for exercises/precurso-measure.png| Determine distances and areas | `M` key |
| **ROI (Region of Interest)**<img width="202" height="51" alt="precurso-roi" src="https://github.com/user-attachments/assets/84752fbc-7fc2-4b20-b106-11b18cf4d99a" />  | Select rectangular, oval, or free-form areas | Toolbar buttons |

#### Excercise

Zoom in as much as you can into a small region. What do you see? Are the squares part of the sample or a rendering? If you hover your mouse over some pixels, what do you see at the bottom grey area of the Fiji main window?

<--!
Students should be able to see the pixels as squares, understand that these correspond to the representation of the matrix of pixels. When hovering the mouse over pixels, Fiji window shows the coordinates in microns (and in pixels), as well as the intensity value.
-->

### Checking Image Properties

After opening an image, first check its header. What are the values on top?

Can you check its metadata? (go to `Image>Show Info...`)

![Show Info Window in Fiji](assets/show_info_window.png)

Fill in the following table:

| Metadata Item | Value |
|---|---|
| Pixel Size (µm) | |
| Magnification | |
| Numerical Aperture (NA) | |
| Bit Depth | |
| Image Dimensions (width × height) | |
| Number of Channels | |
| Number of Slices (if z-stack) | |
| Voxel Dimensions | |
| Unit | |

### Changing the Bit Depth

Images can be stored in different formats representing different levels of intensity information:

- **8-bit** (256 intensity levels) - Smallest file size, fastest processing, good for display
- **16-bit** (65,536 intensity levels) - More detail, larger file size, common in microscopy
- **32-bit** (floating-point) - Highest precision, largest file size, used for calculations

To change the bit depth of your image:

1. Go to `Image > Type` 
2. Select your desired bit depth: `8-bit`, `16-bit`, or `32-bit`
3. If converting from higher to lower bit depth (e.g., 16-bit to 8-bit), you may lose information

#### Exercise

Why might you want to convert a 16-bit image to 8-bit? Consider factors like file size, processing speed, memory usage, and the type of analysis you plan to do. When would it be a bad idea?

<--!
Students should think about trade-offs between data quality and computational efficiency. Converting 16-bit to 8-bit reduces file size and memory footprint, making it useful for large datasets or batch processing. However, it loses intensity information, which could be critical for quantitative analysis requiring fine intensity discrimination. It's generally safe for visualization and qualitative analysis but risky for measurements and quantification. Converting images to 32-bit allows you to perform operations that can result in floating points, such as divisions.
-->

---

## Essential Fiji Functions

### Duplicate an image

Most of the operations are applied on the currently selected image, which might change its intensity values.
Some operations cannot be undone, which means that you have to reopen the image and go through the whole process again if something goes wrong.
To avoid this, it's a good idea to duplicate the image just in case.

Go to `Image > Duplicate`.

### Adjusting Brightness & Contrast

1. `Image > Adjust > Brightness/Contrast...`
2. Drag sliders to enhance visibility
3. Check **Auto** for automatic adjustment
4. Use **Reset** to revert to original

![Brightness and Contrast window](assets/b_and_c_window.png)

*Use case:* Make dim images more visible for analysis.

#### Excercise

Try clicking on **Apply** to see what happens to the pixel values.

### Changing the LookUp Table

Most of the cameras or detectors are monochromatic, which means that the color with which images are represented is a false color.
Go to `Image > LookUp Tables` or click on the LUT button and choose a different color.
What do you think the different palettes are for? Try for example HiLo, cool and 16-colors.

<--!
The students should notice that the LUT is choosen to enhance visibility of what you want to be shown.
Greys are better to distinguish differences in intensity.
Cyan, magenta and greys or yellow might be more color-blind friendly to show superposition of channels.
cool and divergent LUTs are good to show values above vs values below some mid-level.
HiLo is great to notice under- and over-exposure.
16-colors or non-continuous LUTs are good to show labeled images after segmentation.
-->

### Working with more dimensions

First choose an image with several dimension, like a z-stack with more than one channel.
If you don't have one, you can choose `File > Open samples > Mitosis (5D stack)`.

![5D stack image](assets/5d_stack_image.png)

The sliders at the bottom allow you to go through the different channels, z-planes and timepoints.
Some of the sample images already have what is called a composite, where channels are shown simultaneously.
Try doing the following:

#### Split Channels
1. `Image > Color > Split Channels`
2. Each channel opens in a separate window
3. Analyze or process channels independently

#### Merge Channels
1. `Image > Color > Merge Channels`
2. Select source windows for each channel
3. Do not create a composite image

#### Channel Visualization
1. Adjust color assignments for better visualization
2. Go to `Image > Color > Make Composite`

### Quick Measurements

Choose any structure in your image.

#### Plot Intensity Profile

1. Click on **straight line button**
2. Draw a line across your object of interest
3. Go to `Analyze > Plot Profile`
4. Displays intensity values along the line (useful for colocalization studies)

![Line profile image](assets/line_profile_image.png)

![Plot Profile image](assets/plot_profile.png)

What happens if you right click on the straight line button?

<--!
Right clicking allows the user to choose the line width, which lets you draw the mean profile across the line with the chosen width.
-->

#### Measure Intensity
1. Select an ROI (Region of Interest) using selection tools
2. **Analyze → Measure** (or `Ctrl+M`)
3. Results include: Area, Mean intensity, Std Dev, Min, Max

###  Crop
1. Use rectangle selection tool to define region
2. **Image → Crop**
3. Image is reduced to selected area

###  Intensity Histogram
1. Go to **Analyze → Histogram**
2. Click on `Log`

What can you say about the histogram? Is it skewed to the left or right? What is the meximum intensity and how does this relate to the bit-depth? Is 0 the the minimum intensity or which one?

<--!
The histogram tells a lot about the image. In microscopy, most pixels correspond to the background, so a histogram skewed to the right points to a dark field, probably fluorescence microscopy image, while a histogram skewed to the left means that bright pixels are abundant and is likely to come from bright field. A maximum intensity of 255 or lower means that the bit-depth was probably 8-bit, while higher values means that bit-depth was higher. The minimum intensity also tells us something about the offset used and the risk of underexposing the acquisition.
-->

---

