#Scrip de maquina virtual para control de calidad de secuencia de Mycobacterium tuberculosis con acceso ERR2510812

``` Encontrar la secuencia
curl -s "https://www.ebi.ac.uk/ena/portal/api/filereport?accession=ERR2510812&result=read_run&fields=fastq_ftp"
```

``` Descargar la secuencia
wget https://ftp.sra.ebi.ac.uk/vol1/fastq/ERR251/002/ERR2510812/ERR2510812_1.fastq.gz
wget https://ftp.sra.ebi.ac.uk/vol1/fastq/ERR251/002/ERR2510812/ERR2510812_2.fastq.gz
```
``` Control de calidad secuencias crudas
fastqc ERR2510812_1.fastq.gz ERR2510812_2.fastq.gz
```
``` Ver contenido
ls
```
``` Abrir reporte de calidad fastQC de secuencias crudas
xdg-open ERR2510812_1_fastqc.html
xdg-open ERR2510812_2_fastqc.html
```
``` Instalar synaptic
sudo apt-get install synaptic
```
``` Comprobación de instalación de Trimmomatic
dpkg -l | grep trimmomatic
dpkg -L trimmomatic
```
``` Trimming con Trimmomatic
java -jar /usr/share/java/trimmomatic-0.39.jar PE \
  -threads 4 \
  ERR2510812_1.fastq.gz ERR2510812_2.fastq.gz \
  ERR2510812_1_paired.fastq.gz ERR2510812_1_unpaired.fastq.gz \
  ERR2510812_2_paired.fastq.gz ERR2510812_2_unpaired.fastq.gz \
  ILLUMINACLIP:/usr/share/trimmomatic/TruSeq3-PE.fa:2:30:10 \
  LEADING:3 TRAILING:3 SLIDINGWINDOW:4:20 MINLEN:36
```
``` Ver contenido
ls
```
``` Hacer control de calidad a secuencias procesadas
fastqc ERR2510812_1_paired.fastq.gz ERR2510812_2_paired.fastq.gz
```
``` Ver contenido
ls
```
``` Abrir reporte de calidad fastQC de secuencias procesadas
xdg-open ERR2510812_1_paired_fastqc.html
xdg-open ERR2510812_2_paired_fastqc.html
```
