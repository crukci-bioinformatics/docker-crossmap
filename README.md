CrossMap Docker image
=====================

Dockerfile used to create a Docker image for converting genome coordinates between different assemblies using [CrossMap](http://crossmap.sourceforge.net).


### Building the Docker image

To build the Docker image run the following command within the directory containing the Dockerfile:

```
docker build --tag="crukcibioinformatics/crossmap" .
```


### Obtaining a pre-built image

Alternatively, a pre-built image can be obtained from [Docker Hub](https://hub.docker.com/r/crukcibioinformatics/crossmap/) as follows:

```
docker pull crukcibioinformatics/crossmap
```


### Usage

To show the usage instructions for CrossMap:

```
docker run --rm crukcibioinformatics/crossmap CrossMap.py
```

The following shows how to convert a set of intevals in a BED format file from the mm9 mouse assembly to mm10 using a chain file obtained from [UCSC](http://hgdownload.soe.ucsc.edu/downloads.html).

```
docker run --rm -v ${PWD}:/work -w /work crukcibioinformatics/crossmap CrossMap.py bed mm9ToMm10.over.chain.gz targets.mm9.bed targets.mm10.bed
```


