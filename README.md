treebest
========

TreeBeST: Tree Building guided by Species Tree (Ensembl Compara modifications)

This repository holds the necessary changes of [Heng Li's version](https://github.com/lh3/treebest) to run the latest Ensembl Compara pipeline.

You can find more documentation on SourceForge: (http://treesoft.sourceforge.net/treebest.shtml)

The main new features are:
* new "T" node-tag in the NHX output: a bit-field listing the input trees that support the node. This is populated by the _mmerge_ algorithm
* new `-Z` argument to `treebest best`, to redefine the PhyML variable `MIN_DIFF_LK`. It prevents PhyML from crashing during its computation
* new `-s` argument to `treebest sdi`, to allow a user-defined species tree. This change is from [Albert Vilella](https://sites.google.com/site/avilella/)

Other changes include:
* bugfixes / tweaks when processing the filtered alignments (TreeBeST includes a Clustal-score-based MSA-filtering step)
* bugfixes / tweaks when merging the trees
* using `double` instead of `float` for floating-point values
