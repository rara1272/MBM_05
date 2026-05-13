# Proyecto: Evaluación de calidad y análisis filogenético de especies del género Mycobacterium mediante herramientas bioinformáticas

## Integrantes
- Allison Baño
- Kevin Campaña
- Raúl Ramos
- Gabriela Zambrano
- Paulo Franco

## Objetivo general

Integrar herramientas bioinformáticas de control de calidad, preprocesamiento y análisis filogenético para evaluar secuencias genómicas y relaciones evolutivas entre especies del género Mycobacterium mediante datos de secuenciación masiva y secuencias 16S rRNA.

## Objetivos específicos

1.	Evaluar la calidad de lecturas FASTQ de Mycobacterium tuberculosis mediante herramientas bioinformáticas especializadas para identificar errores, adaptadores y regiones de baja calidad en los datos de secuenciación.
2.	Realizar el preprocesamiento y filtrado de secuencias utilizando herramientas de trimming y depuración bioinformática para optimizar la confiabilidad de los análisis posteriores.
3.	Construir e interpretar un árbol filogenético basado en secuencias 16S rRNA de diferentes especies del género Mycobacterium para analizar sus relaciones evolutivas y patrones de agrupamiento molecular.

### 1. Introducción

Las bacterias del género Mycobacterium representan uno de los grupos microbianos de mayor importancia médica y epidemiológica debido a que incluyen especies patógenas responsables de enfermedades como la tuberculosis y diversas micobacteriosis que afectan a humanos y animales a nivel mundial (Cuevas-Córdoba et al., 2021). Mycobacterium tuberculosis continúa siendo una de las principales causas de mortalidad por enfermedades infecciosas, especialmente en países en desarrollo, lo que ha impulsado el uso de herramientas moleculares y bioinformáticas para mejorar su identificación, vigilancia y caracterización genética (World Health Organization [WHO], 2024). Asimismo, la diversidad genética presente dentro del género Mycobacterium permite estudiar procesos evolutivos, relaciones filogenéticas y mecanismos asociados a patogenicidad y adaptación ambiental mediante el análisis de secuencias genómicas y genes conservados como el 16S rRNA (Pozo et al., 2022). En este contexto, el análisis bioinformático constituye una herramienta fundamental para comprender la variabilidad genética y las relaciones evolutivas entre especies bacterianas de importancia clínica y biológica (Peña et al., 2024).

El análisis de secuencias mediante tecnologías de secuenciación de nueva generación (NGS) ha revolucionado el estudio de microorganismos al permitir la obtención masiva de datos genéticos con alta precisión y velocidad (Peña et al., 2024). Sin embargo, las lecturas generadas pueden contener errores de secuenciación, regiones de baja calidad y adaptadores que afectan significativamente la confiabilidad de los análisis posteriores, incluyendo ensamblaje, alineamiento y filogenia (Chen et al., 2018). Por esta razón, el control de calidad y el preprocesamiento de lecturas representan etapas críticas dentro de cualquier flujo de trabajo bioinformático, ya que permiten reducir ruido técnico y mejorar la precisión de los resultados obtenidos (Andrews, 2020). Herramientas especializadas como FastQC y fastp facilitan la evaluación y depuración de secuencias FASTQ mediante análisis de calidad, trimming y filtrado, optimizando la confiabilidad de los estudios genómicos y evolutivos en bacterias patógenas (Chen et al., 2018).

El análisis filogenético basado en secuencias del gen 16S rRNA constituye una metodología ampliamente utilizada para estudiar relaciones evolutivas entre bacterias debido a que este marcador molecular presenta regiones conservadas y variables que permiten diferenciar taxones bacterianos con alta eficiencia (Janda & Abbott, 2021). En especies del género Mycobacterium, la filogenia molecular ha permitido identificar agrupamientos evolutivos, diferenciar especies patógenas y no patógenas, así como comprender patrones de divergencia genética y adaptación biológica (Pozo et al., 2022). Herramientas bioinformáticas como ClustalW y FastTree permiten generar alineamientos múltiples y árboles filogenéticos reproducibles mediante métodos computacionales rápidos y precisos, facilitando la interpretación de relaciones evolutivas entre organismos microbianos (Price et al., 2020). Estos enfoques son actualmente indispensables en investigaciones relacionadas con microbiología, epidemiología molecular y vigilancia genómica de enfermedades infecciosas (Cuevas-Córdoba et al., 2021).

El presente proyecto tiene como finalidad integrar herramientas de control de calidad, procesamiento de secuencias y análisis filogenético para evaluar especies del género Mycobacterium mediante un enfoque bioinformático reproducible. Para ello, se emplearán secuencias FASTQ y secuencias 16S rRNA obtenidas desde bases de datos públicas como NCBI, utilizando plataformas y herramientas especializadas como Galaxy, FastQC, fastp, ClustalW y FastTree para desarrollar el flujo de trabajo bioinformático (Chen et al., 2018). El análisis permitirá comparar la calidad de las lecturas antes y después del preprocesamiento, además de interpretar relaciones filogenéticas entre especies del género Mycobacterium mediante la construcción de árboles evolutivos (Price et al., 2020). De esta manera, el estudio busca demostrar la importancia del control de calidad y de las herramientas bioinformáticas modernas para generar resultados confiables, reproducibles y biológicamente interpretables en investigaciones microbiológicas y genómicas (Peña et al., 2024).

### 2. Metodología

La investigación se desarrolló mediante un enfoque bioinformático aplicado al análisis de secuencias del género Mycobacterium, utilizando datos genómicos obtenidos desde bases de datos públicas del National Center for Biotechnology Information (NCBI). Para el análisis de control de calidad y preprocesamiento se emplearon lecturas paired-end de Mycobacterium tuberculosis descargadas desde el Sequence Read Archive (SRA), correspondientes a los accesos SRR38455387, SRR38455388 y SRR38455389 . Las secuencias fueron importadas y procesadas en la plataforma Galaxy debido a su capacidad para desarrollar flujos de trabajo reproducibles y accesibles en análisis de secuenciación masiva (Afgan et al., 2022). Inicialmente, la calidad de las lecturas FASTQ fue evaluada mediante la herramienta FastQC, la cual permitió analizar parámetros como calidad por base, contenido GC, secuencias duplicadas y presencia de adaptadores (Andrews, 2020). Posteriormente, se realizó el preprocesamiento y filtrado utilizando fastp para eliminar lecturas de baja calidad, adaptadores y ruido técnico, optimizando la confiabilidad de los análisis posteriores (Chen et al., 2018).

Para el análisis filogenético se utilizaron secuencias del gen 16S rRNA correspondientes a diferentes especies del género Mycobacterium, incluyendo Mycobacterium tuberculosis, Mycobacterium bovis, Mycobacterium smegmatis, Mycobacterium africanum y Mycobacterium avium, obtenidas desde GenBank en formato FASTA . Previo al análisis, las secuencias fueron sometidas a un proceso de curación manual que incluyó revisión de headers, verificación de longitud y detección de caracteres ambiguos, con el propósito de garantizar la integridad y consistencia del dataset biológico (Janda & Abbott, 2021). Posteriormente, se realizó un alineamiento múltiple de secuencias mediante ClustalW, herramienta ampliamente utilizada para identificar regiones conservadas y variables entre organismos bacterianos (Larkin et al., 2007). Finalmente, los alineamientos fueron procesados mediante FastTree para generar árboles filogenéticos basados en máxima verosimilitud aproximada, permitiendo inferir relaciones evolutivas entre las especies analizadas (Price et al., 2020).

El flujo de trabajo bioinformático implementado integró herramientas de análisis de calidad, procesamiento y filogenia con el objetivo de garantizar reproducibilidad, confiabilidad e interpretación biológica de los resultados obtenidos . La comparación de métricas de calidad antes y después del preprocesamiento permitió evaluar la efectividad del filtrado y trimming sobre las lecturas de secuenciación, considerando indicadores como calidad promedio, reducción de adaptadores y distribución de bases ambiguas (Chen et al., 2018). Asimismo, la construcción del árbol filogenético permitió analizar patrones de agrupamiento molecular y cercanía evolutiva entre especies del género Mycobacterium, facilitando la interpretación de procesos de divergencia genética y conservación evolutiva (Cuevas-Córdoba et al., 2021). De esta manera, la metodología empleada permitió integrar herramientas bioinformáticas modernas para desarrollar un análisis microbiológico robusto y reproducible orientado al estudio evolutivo y genómico de bacterias de importancia médica.

### 3. Resultados
tablas 
gráficos
interpretación biológica 

### 4. Discusión
interpretación biológica (citar) 

### 5. Conclusiones  

### 6. Referencias bibliográficas  
Genere un grupo en Mendeley con sus compañeros de proyecto. Coloque todas sus fuentes y los respectivos PDFs de cada una  
## NOTA
:eyes: Deberá invitarme a su grupo en Mendeley o las plataformas usadas al correo bioupsmantigua@gmail.com
