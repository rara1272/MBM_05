Scrip de maquina virtual para control de calidad de secuencia de Mycobacterium tuberculosis con acceso ERR2510812

alex@alex-virtualbox:~$ curl -s "https://www.ebi.ac.uk/ena/portal/api/filereport?accession=ERR2510812&result=read_run&fields=fastq_ftp"
alex@alex-virtualbox:~$ wget https://ftp.sra.ebi.ac.uk/vol1/fastq/ERR251/002/ERR2510812/ERR2510812_1.fastq.gz
wget https://ftp.sra.ebi.ac.uk/vol1/fastq/ERR251/002/ERR2510812/ERR2510812_2.fastq.gz
alex@alex-virtualbox:~$ fastqc ERR2510812_1.fastq.gz ERR2510812_2.fastq.gz
alex@alex-virtualbox:~$ ls
alex@alex-virtualbox:~$ xdg-open ERR2510812_1_fastqc.html
alex@alex-virtualbox:~$ xdg-open ERR2510812_2_fastqc.html
alex@alex-virtualbox:~$ sudo apt-get install synaptic
alex@alex-virtualbox:~$ dpkg -l | grep trimmomatic
alex@alex-virtualbox:~$ dpkg -L trimmomatic
alex@alex-virtualbox:~$ java -jar /usr/share/java/trimmomatic-0.39.jar PE \
  -threads 4 \
  ERR2510812_1.fastq.gz ERR2510812_2.fastq.gz \
  ERR2510812_1_paired.fastq.gz ERR2510812_1_unpaired.fastq.gz \
  ERR2510812_2_paired.fastq.gz ERR2510812_2_unpaired.fastq.gz \
  ILLUMINACLIP:/usr/share/trimmomatic/TruSeq3-PE.fa:2:30:10 \
  LEADING:3 TRAILING:3 SLIDINGWINDOW:4:20 MINLEN:36
alex@alex-virtualbox:~$ ls
alex@alex-virtualbox:~$ fastqc ERR2510812_1_paired.fastq.gz ERR2510812_2_paired.fastq.gz
alex@alex-virtualbox:~$ ls
alex@alex-virtualbox:~$ xdg-open ERR2510812_1_paired_fastqc.html
xdg-open ERR2510812_2_paired_fastqc.html
