# Análisis transcriptómico de células LSK con mutación R396Q en GATA2 mediante scRNA-seq

título del reporte; integrantes y programa cursado; fecha, materia y semestre; abstract del trabajo; enlace al reporte renderizado; explicación detallada de los pasos y scripts; y referencias utilizadas.

**Autoras:** Victoria Lelis, Renata Sandoval y Ariana Silva

Junio, 2026

**Curso:** Bioinformática aplicada al análisis de transcriptómica diferencial

Octavo semestre de la Licenciatura en Ciencias Genómicas, Universidad Nacional Autónoma de México, Unidad Juriquilla

**Docentes del curso de bioinformática:** Dra. Evelia Coss, Dr. Jerónimo Miranda, Dr. Wilbert Gutiérrez

Este es un repositorio en el que describimos paso a paso el proceso llevado a cabo durante el análisis bioinformático del proyecto enfocado en secuenciación de ARN a nivel de célula única.

Como contexto general del análisis, a continuación se describe el contexto biológico del estudio, las características de los datos analizados y los principales enfoques bioinformáticos empleados para responder las preguntas de investigación planteadas.

## Resumen

En este proyecto se compararon células LSK de ratón de dos grupos: wild type (WT, sin mutaciones) y portadoras de la mutación R396Q en *Gata2*, la cual ha sido asociada en estudios previos con la progresión de la deficiencia de Gata2 hacia leucemia. Los datos analizados son de tipo single-cell RNA-seq (scRNA-seq), generados mediante la plataforma Chromium 10x Genomics (v3.1) y secuenciados con Illumina NovaSeq en modalidad paired-end, a una profundidad mínima de 50,000 lecturas por célula. Para el análisis bioinformático se utilizaron Seurat y Harmony del pipeline original, para el filtrado, normalización, clustering, UMAP, expresión diferencial e integración de réplicas, respectivamente. Adicionalmente, se incorporaron SingleR con celldex para la anotación de tipos celulares, DoubletFinder para detección de dobletes y edgeR para expresión diferencial con enfoque pseudobulk. Se confirmaron genes previamente reportados como sobreexpresados en células mutantes, validando la reproducibilidad del pipeline. Además, se identificaron genes adicionales como Mertk, regulado a la baja en mutantes y vinculado a la señalización y homeostasis en progenitores hematopoyéticos, los cuales complementan lo ya descrito sobre el efecto de la mutación R396Q en *Gata2* y aportan nuevas perspectivas sobre los procesos metabólicos implicados en la transición hacia un estado leucémico.

De la misma manera, se recomienda encarecidamente leer la información general del código en el siguiente [apartado](https://github.com/arianaresi/scRNA-seq-Analysis/tree/main/Descripción/InformacionGeneral.qmd).

## Visión general

**1. Descarga y normalización de datos**

Las matrices de cuentas sin procesar (códigos de barras, características, matriz) de 8 muestras (4 WT + 4 mutantes R396Q) se descargaron directamente de NCBI GEO. Cada muestra se convierte en un objeto Seurat y, a continuación, se fusiona en un único objeto para su análisis de calidad y normalización en conjunto. 

El script .qmd y archivo HTML pueden consultarse [aquí]().


Traducción realizada con la versión gratuita del traductor DeepL.com

It is a folder containing scripts and explanations of the outputs of each of the steps mentioned below, you can check out it [here](https://github.com/arianaresi/RNA-seq-Project/tree/main/Raw%20data).

In addition, each of the specific steps during this process can be reviewed by clicking on the desired title:

- [Download](https://github.com/arianaresi/RNA-seq-Project/blob/main/Raw%20data/Download.md)
- [Fastqc](https://github.com/arianaresi/RNA-seq-Project/blob/main/Raw%20data/FastQC_RawData.md)
- [Multiqc](https://github.com/arianaresi/RNA-seq-Project/blob/main/Raw%20data/MultiQC_RawData.md)

**2. Trimming**

It is a folder containing scripts and explanations of the outputs of each of the steps mentioned below, you can check out it in the [Trimming directory](https://github.com/arianaresi/RNA-seq-Project/tree/main/Trimming).

In addition, each of the specific steps during the Trimming process can be reviewed by clicking on the desired title:

   - [Results](https://github.com/arianaresi/RNA-seq-Project/blob/main/Trimming/Trimming_code_and_results.md)
   - [Fastqc](https://github.com/arianaresi/RNA-seq-Project/blob/main/Trimming/FastQC_trimmed.md)
   - [Multiqc](https://github.com/arianaresi/RNA-seq-Project/blob/main/Trimming/MultiQC_trimmed.md)

**3. Alignment**

It is a folder containing scripts and explanations of the outputs of each of the steps mentioned below, you can check out it in the [Alignment](https://github.com/arianaresi/RNA-seq-Project/tree/main/Alignment) directory.

   - [Definition and workflow](https://github.com/arianaresi/RNA-seq-Project/blob/main/Alignment/Definition%20and%20workflow.md)
   - [STAR index](https://github.com/arianaresi/RNA-seq-Project/blob/main/Alignment/STAR_index.md)
   - [STAR alignment](https://github.com/arianaresi/RNA-seq-Project/blob/main/Alignment/STAR_alignment.md)
  
**4. R analysis**

The complete code diretory can be found [here](https://github.com/arianaresi/RNA-seq-Project/tree/main/R%20analysis).

A single code was made for import data into R, Normalization and Batch effect correction / DGE analysis you can check out it [here](https://github.com/arianaresi/RNA-seq-Project/blob/main/R%20analysis/script_complet.txt). 

   - [Import STAR data to R](https://github.com/arianaresi/RNA-seq-Project/blob/main/R%20analysis/Import%20data/Import_data_R.md)
   - [Normalization](https://github.com/arianaresi/RNA-seq-Project/blob/main/R%20analysis/Normalization.md)
   - [Batch effect correction](https://github.com/arianaresi/RNA-seq-Project/blob/main/R%20analysis/Batch_effect_correction.md)
   - [DGE Analysis (DESeq2)](https://github.com/arianaresi/RNA-seq-Project/blob/main/R%20analysis/DGE_analysis.md)
  
**5. Analysis of Functional Terms (GOterms)**

It is a folder containing scripts and explanations of the outputs of each of the steps mentioned below, you can check out it in the [GOterms](https://github.com/arianaresi/RNA-seq-Project/tree/main/Analysis%20of%20Functional%20Terms) directory.
- [GOt
