# BUSCO-Phylogenomics

<a href="https://jamiemcgowan.ie" target="_blank">Jamie McGowan - 2019</a>

Utility script to construct species phylogenies using BUSCOs. Works directly from BUSCO output and can be used for supermatrix or supertree methods.

This pipeline runs directly on the output from BUSCO. Move results directories from each BUSCO run (begins with "run_" by default) into the same directory. Example structure, where `INPUT_DIRECTORY` is passed to the `-d` parameter of the pipeline:

* INPUT_DIRECTORY
	* run_species1
	* run_species2
	* run_species3
	* run_species4
	* run_species5
	* run_species6
	* ........


### Usage
	python BUSCO_Phylogenomics.py -d INPUT_DIRECTORY -o OUTPUT_DIRECTORY --supermatrix --threads 20
	
	
	
### Required parameters:
* `-d --directory` input directory containing BUSCO runs
* `-o --output` output directory
* `-t --threads` number of threads to use
* `--supermatrix` and/or `--supertree` choose to run supermatrix and/or supertree methods


### Optional parameters
* `-psc` BUSCO families that are present and single-copy in N% of species will be included in supermatrix analysis [default = 100%]
* `--stop_early` stop pipeline early before phylogenetic inference


### Requirements
* [Python](https://www.python.org/)
* [BioPython](https://biopython.org/)
* [MUSCLE](https://www.drive5.com/muscle/)
* [trimAl](http://trimal.cgenomics.org/)
* [IQ-TREE](http://www.iqtree.org/)


`muscle`, `trimal` and `iqtree` should be in `$PATH`


### Pipeline
![BUSCO Phylogenomics pipeline](./pipeline.png)


