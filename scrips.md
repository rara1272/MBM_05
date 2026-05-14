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

Scrip árbol filogénico

alex@alex-virtualbox:~$ nano micobacterias.fasta
alex@alex-virtualbox:~$ nano micobacterias.fasta
alex@alex-virtualbox:~$ ls -l micobacterias.fasta
cat micobacterias.fasta
alex@alex-virtualbox:~$ sudo apt update
sudo apt install mafft fasttree
alex@alex-virtualbox:~$ mafft --auto micobacterias.fasta > micobacterias_alineadas.fasta
alex@alex-virtualbox:~$ fasttree -nt micobacterias_alineadas.fasta > arbol_micobacterias.nwk
alex@alex-virtualbox:~$ sudo apt install newick-utils
alex@alex-virtualbox:~$ nw_display arbol_micobacterias.nwk
alex@alex-virtualbox:~$ mafft --anysymbol --auto micobacterias.fasta > micobacterias_alineadas.fasta
alex@alex-virtualbox:~$ fasttree -nt micobacterias_alineadas.fasta > arbol_micobacterias.nwk
alex@alex-virtualbox:~$ pip install ete3
python3 -c "from ete3 import Tree; t=Tree('arbol_micobacterias.nwk'); print(t.get_ascii(show_internal=True))"
alex@alex-virtualbox:~$ figtree arbol_micobacterias.nwk
alex@alex-virtualbox:~$ sudo apt update
sudo apt install python3-pip
alex@alex-virtualbox:~$ pip3 --version
alex@alex-virtualbox:~$ pip3 install ete3
alex@alex-virtualbox:~$ python3 -c "from ete3 import Tree; t=Tree('arbol_micobacterias.nwk'); print(t.get_ascii(show_internal=True))"
alex@alex-virtualbox:~$ sudo apt install figtree
alex@alex-virtualbox:~$ figtree arbol_micobacterias.nwk
