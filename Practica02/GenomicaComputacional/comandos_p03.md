# Comandos de la Práctica 01
**Joanna Lizeth Sánchez Rangel**

## Parte I. 

**Respuesta 1:** Creación de directorios y archivos.
<br/><br/>
Comandos: 
<br/><br/>
$cd Escritorio/
<br/><br/>
$mkdir GenomicaComputacional
<br/><br/>
$mkdir jsanchez_p03
<br/><br/>
$touch comandos_p03.md

**Respuesta 2:** Tipo de shell.
<br/><br/>
Comando:
<br/><br/>
$echo $0 
<br/><br/>
Output:
<br/><br/>
bash
<br/><br/>
Hace referencia a Bourne Again Shell.

**Respuesta 3:** Creación de directorios para proyecto bioinformático.
<br/><br/>
Comandos:
<br/><br/>
$cd jsanchez_p03/
<br/><br/>
$mkdir data/ filtered/ raw_data/ meta/ scripts/ figures/ archive/
<br/><br/>
$mv ./filtered ./data
<br/><br/>
$mv ./raw_data ./data

**Respuesta 4:**
<br/><br/>
Sirve para tener una buena organización de todo lo que implica el proyecto.
<br/><br/>
En este caso, el nombre del directorio donde se encuentra el proyecto es jsanchez_p03.
<br/><br/>
La organización del proyecto se compone de los subdirectorios:
<br/><br/>
- archive: Se guardan scripts o resultados importantes que se obtuvieron a lo largo del proyecto pero que no
         son parte de, por lo tanto se guardan aquí para investigarlos después. Este subdirectorio no se sube
         al repositorio final del proyecto.
- data: Contiene los datos Genéticos. Debido a que se tienen distintos tipos de datos, se crean más subdirectorios
      para éstos.
  - filtered: Son los datos a los que se les hicieron modificaciones para hacer análisis de ellos.
  - raw_data: Son los datos crudos, es decir los datos originales sin ninguna modificación.
- figures: Aquí se guardan las partes de código para las figuras que estarán en la publicación.
- meta: Aquí se guardan todos los metadatos, como lo son los documentos que guardan la información
         de las muestras .
- scripts: Se guardan todos los scripts necesarios para correr el análisis de principio a fin.

## Parte II.
**Respuesta 1:**
<br/><br/>
$cd scripts/
<br/><br/>
$touch delay.sh
<br/><br/>
$nano delay.sh

**Respuesta 2:**
$chmod 777 delay.sh

**Respuesta 3:**
<br/><br/>
$ls -lth delay.sh  
<br/><br/>
Output: -rwxrwxrwx 1 joanna joanna 92 dic  6 12:21 delay.sh
<br/><br/>
$sh delay.sh

**Respuesta 4:**
<br/><br/>
$sleep 30

**Respuesta 5:**
<br/><br/>
$sleep 300 &
<br/><br/>
$kill -9 9380

## Parte III.
**Respuesta 2:**
<br/><br/>
$mv sarscov2_genome.fasta ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv splike_a.faa ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv splike_c.faa ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv sarscov2_assembly.fasta.gz ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv sarscov2_genome.gff3 ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv splike_b.faa ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv SRR10971381_R1.fastq.gz ./GenomicaComputacional/jsanchez_p03/data/raw_data/
<br/><br/>
$mv SRR10971381_R2.fastq.gz ./GenomicaComputacional/jsanchez_p03/data/raw_data/

## Parte IV.

**Respuesta 1:**
<br/><br/>
$ln -s ./data/raw_data/splike_a.faa ./data/filtered/
<br/><br/>
$ln -s ./data/raw_data/splike_b.faa ./data/filtered/
<br/><br/>
$ln -s ./data/raw_data/splike_c.faa ./data/filtered/

**Respuesta 2:**
<br/><br/>
$cd data/filtered/
<br/><br/>
$touch glycoproteins.faa

**Respuesta 3:**
<br/><br/>
$head -n 1 ./jsanchez_p03/data/raw_data/splike_a.faa
<br/><br/>
$head -n 1 ./jsanchez_p03/data/raw_data/splike_b.faa
<br/><br/>
$head -n 1 ./jsanchez_p03/data/raw_data/splike_c.faa

**Respuesta 4:**
<br/><br/>
$cat ./data/raw_data/splike_a.faa >> ./data/filtered/glycoproteins.faa
<br/><br/>
$cat ./data/raw_data/splike_b.faa >> ./data/filtered/glycoproteins.faa
<br/><br/>
$cat ./data/raw_data/splike_c.faa >> ./data/filtered/glycoproteins.faa

**Respuesta 5:**
<br/><br/>
$mv ./data/raw_data/splike_*.faa ./archive
<br/><br/>
Las ligas simbólicas suaves siguen ahí, sin embargo al intentar abrir el enlace, se presenta en pantalla un mensaje
diciendo que el enlace no se puede usar porque el directorio ./data/raw_data/splike_*.faa no existe.

**Respuesta 6:**
<br/><br/>
$cd data/raw_data/
<br/><br/>
$head -3 sarscov2_genome.fasta
<br/><br/>
$head -3 sarscov2_assembly.fasta.gz

**Respuesta 7:**
<br/><br/>
$grep -o '>' sarscov2_genome.fasta | wc -l
<br/><br/>
$grep -o '>' sarscov2_assembly.fasta.gz | wc -l
<br/><br/>
Cada archivo tiene un solo header.

**Respuesta 8:**
<br/><br/>
$grep -o '@' SRR10971381_R2.fastq.gz | wc -l

**Respuesta 9:**
<br/><br/>
El formato .faa es usado por NCBI y hace referencia a aminoácidos.
<br/><br/>
El formato .fasta se usa para representar secuencias de ácidos nucleicos.
<br/><br/>
El formato .fastq son archivos que contienen los datos de secuencia.

**Respuesta 10:**
<br/><br/>
La diferencia entre usar less sarscov2_genome.gff3 y less -S sarscov2_genome.gff3, es que
la primera presenta toda la información y la segunda agrupa la información en columnas.

## Parte V. 

**Respuesta 1:**
<br/><br/>
$cd figures/
<br/><br/>
$ln -s ./data/raw_data/sarscov2_genome.gff3
