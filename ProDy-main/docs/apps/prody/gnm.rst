.. _prody-gnm:

prody gnm
====================

Usage
--------------------

Running :command:`prody gnm -h` displays::

  usage: prody gnm [-h] [--quiet] [--examples] [-n INT] [-s SEL] [-c FLOAT]
                   [-g FLOAT] [-m INT] [-a] [-o PATH] [-e] [-r] [-u] [-q] [-v]
                   [-z] [-t STR] [-b] [-k] [-p STR] [-f STR] [-d STR] [-x STR]
                   [-A] [-R] [-Q] [-B] [-K] [-M STR] [-F STR] [-D INT]
                   [-W FLOAT] [-H FLOAT]
                   pdb
  
  positional arguments:
    pdb                   PDB identifier or filename
  
  optional arguments:
    -h, --help            show this help message and exit
    --quiet               suppress info messages to stderr
    --examples            show usage examples and exit
  
  parameters:
    -n INT, --number-of-modes INT
                          number of non-zero eigenvectors (modes) to calculate
                          (default: 10)
    -s SEL, --select SEL  atom selection (default: "protein and name CA or
                          nucleic and name P C4' C2")
    -c FLOAT, --cutoff FLOAT
                          cutoff distance (A) (default: 10.0)
    -g FLOAT, --gamma FLOAT
                          spring constant (default: 1.0)
    -m INT, --model INT   index of model that will be used in the calculations
  
  output:
    -a, --all-output      write all outputs
    -o PATH, --output-dir PATH
                          output directory (default: .)
    -e, --eigenvs         write eigenvalues/vectors
    -r, --cross-correlations
                          write cross-correlations
    -u, --heatmap         write cross-correlations heatmap file
    -q, --square-fluctuations
                          write square-fluctuations
    -v, --covariance      write covariance matrix
    -z, --npz             write compressed ProDy data file
    -t STR, --extend STR  write NMD file for the model extended to "backbone"
                          ("bb") or "all" atoms of the residue, model must have
                          one node per residue
    -b, --beta-factors    write beta-factors calculated from GNM modes
    -k, --kirchhoff       write Kirchhoff matrix
  
  output options:
    -p STR, --file-prefix STR
                          output file prefix (default: pdb_gnm)
    -f STR, --number-format STR
                          number output format (default: %12g)
    -d STR, --delimiter STR
                          number delimiter (default: " ")
    -x STR, --extension STR
                          numeric file extension (default: .txt)
  
  figures:
    -A, --all-figures     save all figures
    -R, --cross-correlations-figure
                          save cross-correlations figure
    -Q, --square-fluctuations-figure
                          save square-fluctuations figure
    -B, --beta-factors-figure
                          save beta-factors figure
    -K, --contact-map     save contact map (Kirchhoff matrix) figure
    -M STR, --mode-shape-figure STR
                          save mode shape figures for specified modes, e.g. "1-3
                          5" for modes 1, 2, 3 and 5
  
  figure options:
    -F STR, --figure-format STR
                          pdf (default: pdf)
    -D INT, --dpi INT     figure resolution (dpi) (default: 300)
    -W FLOAT, --width FLOAT
                          figure width (inch) (default: 8.0)
    -H FLOAT, --height FLOAT
                          figure height (inch) (default: 6.0)

Examples
--------------------

Running :command:`prody gnm --examples` displays::

  This command performs GNM calculations for given PDB structure and
  outputs results in NMD format. If an identifier is passed, structure
  file will be downloaded from the PDB FTP server.
  
  Fetch PDB 1p38, run GNM calculations using default parameters, and
  results:
  
    $ prody gnm 1p38
  
  Fetch PDB 1aar, run GNM calculations with cutoff distance 7 angstrom
  for chain A carbon alpha atoms with residue numbers less than 70, and
  save all of the graphical output files:
  
    $ prody gnm 1aar -c 7 -s "calpha and chain A and resnum < 70" -A
  
