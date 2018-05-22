# Council of Canadian Academies
## Competing in a Global Ecomony: The state of Research & Development in Canada
This ReadMe describes how to generate many of the figures used in the CCA 2017 report.  To extract the files from the tarball:
`unzip -p CCA_2017_CGErpt.tar.zip | tar -xf -`
The graphics were designed on MacOSX Sierra (10.12.6+) and MacOSX High Sierra (10.13.1+), and the tarball was created using *bsdtar 2.8.3 - libarchive 2.8.3* and *Zip 3.0*.  Once extracted, the directory structure should look like this:
* Readme.md
* fontFix.sh
* matplotlibrc
* definitions.py
* header/
* report/
* ------/chap2/ 
* ------/chap3/ 
* ------/chap4/ 
* ------/chap5/ 
* ------/chap6/ 
* ------/appendix/ 
* data/
* tables/
The Readme is a copy of this one.  The rest of the files and directories will be discussed in greater detail below.  The graphics make use of `python3.*`, as well as the `NumPy`, `SciPy`, `matplotlib`, and `pandas`.
### fontFix.sh
In MacOS, font styles are stored within a tree, as opposed to Windows where they are stored individually.  As such, when SVGs are written on a Mac the font styling may be that of the tree root, rather than the specific branch.  This bash script loops over every SVG file in the directory and uses sed and RegEx to replace the root font styling with the intended font styles.  It also removes the backup files.
### matplotlibrc
This RC file correctly mimics the Council of Canadian Academies graph styling.  A copy needs to be placed in every directory that contains python scripts creating graphics.
### definitions.py
This is the initialization script for the graphics.  It imports the important packages, defines the colour styling for the report, and the `matplotlib.fontmanager` font stylings.  The directory strings at the beginning of the file also need to be set for the user.
### subdirectories
The subdirectories should be self explanatory.
