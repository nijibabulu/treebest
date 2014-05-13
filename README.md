treebest
========

TreeBeST: Tree Building guided by Species Tree (Ensembl Compara modifications)

This repository holds the necessary changes of [Heng Li's version](https://github.com/lh3/treebest) to run the latest Ensembl Compara pipeline.

You can find more documentation on SourceForge: (http://treesoft.sourceforge.net/treebest.shtml)

The main new features are:
* new "T" node-tag in the NHX output: a bit-field listing the input trees that support the node. This is populated by the _mmerge_ algorithm
* new `-Z` argument to `treebest best`, to redefine the PhyML variable `MIN_DIFF_LK`. It prevents PhyML from crashing during its computation
* new `-s` argument to `treebest sdi`, to allow a user-defined species tree. This change is from [Albert Vilella](https://sites.google.com/site/avilella/)
* new `-X` argument to `treebest best`, to give a higher weight to the likelihood that comes from the reconciliation with the species tree (default 1)
* Species-Intersection Scores are now reported as floating-point values (with 2 decimals)

Other changes include:
* bugfixes / tweaks when processing the filtered alignments (TreeBeST includes a Clustal-score-based MSA-filtering step)
* bugfixes / tweaks when merging the trees
* using `double` instead of `float` for floating-point values

## Branches and tags

There is a single branch where all the development goes. The version number stated in the source code (1.9.2) is not maintained.

Tags are used to point at specific versions:
* lh3 (currently 2a4fe3): when Heng Li handed-over the code to Ensembl Compara
* albert (currently 5e20c4): changes made by [Albert Vilella](https://sites.google.com/site/avilella/)
* ensembl\_production (currently 24637d): the version currently used for Ensembl's production
