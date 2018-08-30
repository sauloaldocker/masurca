
## TO BUILD
`docker build -t sauloal/masurca .`

## TO RUN MANUALLY :
### FROM INSIDE THE FOLDER CONTAINING THE MOUSE DATA, RUN:
`chmod o+w .`
`docker run --rm -it --name masurca_mouse -v $PWD:/data:rw sauloal/masurca bash`
`masurca mm_config.cfg`
`./assembly.sh`


## TO RUN AUTOMATICALLY
### FROM INSIDE THE FOLDER CONTAINING THE MOUSE DATA, RUN:
`chmod o+w .`
`docker run --rm -it --name masurca_mouse -v $PWD:/data:rw sauloal/masurca masurca mm_config.cfg`
`docker run --rm -it --name masurca_mouse -v $PWD:/data:rw sauloal/masurca ./assembly.sh`

## Example configuration file
### mm_config.cfg

> DATA

> PE= pe 180 20 /data/pe_1.fastq /data/pe_2.fastq

> JUMP= j1 1834 182 /data/sj_1834_182_1.fastq /data/sj_1834_182_2.fastq

> JUMP= j2 2289 2794 /data/sj_2289_212_1.fastq /data/sj_2289_212_2.fastq

> JUMP= j3 2794 220 /data/sj_2794_220_1.fastq /data/sj_2794_220_2.fastq

> JUMP= j4 -38453 3557 /data/lj_38453_3557_2.fastq /data/lj_38453_3557_1.fastq

> END

> GRAPH_KMER_SIZE=auto

> USE_LINKING_MATES=0

> LIMIT_JUMP_COVERAGE = 60

> CA_PARAMETERS = ovlMerSize=30 cgwErrorRate=0.10 ovlMemory=40GB

> KMER_COUNT_THRESHOLD = 1

> NUM_THREADS= 20

> JF_SIZE=10000000000

> DO_HOMOPOLYMER_TRIM=0

> END
