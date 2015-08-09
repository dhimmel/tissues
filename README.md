# Gene–Tissue relationships from the TISSUES database

TISSUES is a database of gene–tissue relationships that combines many lines of evidence. Learn more about TISSUES from its [website](http://tissues.jensenlab.org/) or [publication](https://dx.doi.org/10.7717/peerj.1054).

This repository creates a single tsv-formatted table ([`merged.tsv.gz`](data/merged.tsv.gz)) from the TISSUES datasets. Tissues are converted from BTO to Uberon identifiers. Genes are converted from STRING/Ensembl identifiers to Entrez Gene. We compute two integrated experimental scores not available from the [Jensen lab downloads](http://download.jensenlab.org/): `score_experiment` and `score_experiment_unbiased`, which [excludes](http://thinklab.com/discussion/the-tissues-resource-for-the-tissue-specificity-of-genes/91#6) HPA-IHC data.

For more information, see the corresponding [Thinklab discussion](http://thinklab.com/discussion/the-tissues-resource-for-the-tissue-specificity-of-genes/91).

All computation is performed by the [`TISSUES.ipynb`](TISSUES.ipynb) notebook. Code was written for Python 3.4.
