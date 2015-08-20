gbeer_standalone
==========

Overview
--------

gbeer_standalone is a tool to quantify and visualize the evolutionary changes that occur in gene blocks.
gbeer_standalone is designed to be run from the command line, or as part of a web installation, and has tools
and options designed to accomodate these two roles. 

Released under GPL version 3 licence. See http://www.gnu.org/licenses/lgpl.html or
LICENSE for more details.

Requirements
------------
* Python 2.7.6+
* Biopython 1.63+ (python-biopython)
* matplotlib 1.4.3+ (python-matplotlib)
* Levenshtein (python-levenshtein)
* ClustalW (clustalw) - likely replaced with ClustalOmega (clustalo)
* ncbi-tools (ncbi-tools-bin)
* BLAST2 (blast2)
To be tested as requirements
* BLAST+ (ncbi-blast+) - this might not be necessary, i am going to check this dependency explicitly soon
* CD-hit (cd-hit) - not required yet, but will be soon


```bash
apt-get install python-biopython python-matplotlib python-levenshtein clustalw ncbi-tools-bin blast2 ncbi-blast+ cd-hit
```


The easiest way to run the project is to execute the script named 'gbeer_standalone.py'.  The defaults
that are provided are sufficient to run the project with the inputs provided.
Each accompanying script can be run on its own as well.  gbeer_standalone.py does not allow for the intermediate
files or folders to be renamed by the user.  Currently the user cannot select the point that analysis
begins at though this could become a feaure later.


gbeer_standalone.py -h
usage: gbeer_standalone.py [-h] [-i FILE] [-G DIRECTORY] [-o DIRECTORY]
                           [-f FILE] [-n INT] [-m INT] [-g INT] [-e FLOAT]
                           [-t FILE] [-c] [-q]

The purpose of this script is to run the full software suite that we have
developed to study gene blocks using as few inputs as possible. This will
facilitate the ease of use as much as possible.

optional arguments:
  -h, --help            show this help message and exit
  -i FILE, --gene_block_file FILE
                        Input file for the gene block query step of the
                        pipeline.
  -G DIRECTORY, --genbank_directory DIRECTORY
                        Folder containing all genbank files for use by the
                        program.
  -o DIRECTORY, --outfolder DIRECTORY
                        Folder where results will be stored.
  -f FILE, --filter FILE
                        File restrictiong which accession numbers this script
                        will process. If no file is provided, filtering is not
                        performed.
  -n INT, --num_proc INT
                        Number of processors that you want this script to run
                        on. The default is every CPU that the system has.
  -m INT, --min_genes INT
                        Minum number of genes that an gene_block must contain
                        before it can be considered for further analysis. The
                        default is 5 because that is what we are currently
                        using in the study.
  -g INT, --max_gap INT
                        Size in nucleotides of the maximum gap allowed between
                        genes to be considered neighboring. The default is
                        500.
  -e FLOAT, --eval FLOAT
                        eval for the BLAST search.
  -t FILE, --tree FILE  Newick format tree file which will be used to bypass
                        tree creation.
  -c, --clean           Flag to toggle the removal of intermediate files that
                        are unnecessary for analysis, reducing the storage
                        requirements for a run.
  -q, --quiet           Suppresses most program text outputs.

>>>>>>> f3a44d21adccfd356de425f0cd080b351378175d
