# Gene–Tissue relationships from the TISSUES database

TISSUES is a database of gene–tissue relationships that combines many lines of evidence. Learn more about TISSUES from its [website](http://tissues.jensenlab.org/) or [publication](https://dx.doi.org/10.7717/peerj.1054).

This repository creates a single tsv-formatted table ([`merged.tsv.gz`](data/merged.tsv.gz)) from the TISSUES datasets. Tissues are converted from BTO to Uberon identifiers. Genes are converted from STRING/Ensembl identifiers to Entrez Gene. We compute two integrated experimental scores not available from the [Jensen lab downloads](http://download.jensenlab.org/): `score_experiment` and `score_experiment_unbiased`, which [excludes](http://thinklab.com/discussion/the-tissues-resource-for-the-tissue-specificity-of-genes/91#6) HPA-IHC data.

`merged.tsv.gz` is formatted like:

| uberon_id | uberon_name | entrez_gene_id | gene_symbol | score_text | score_knowledge | score_experiment | score_experiment_unbiased | score_integrated |
|----------------|----------------|----------------|-------------|------------|-----------------|------------------|---------------------------|------------------|
| UBERON:0000002 | uterine cervix | 2 | A2M | 0.8 |  | 0 |  | 1 |
| UBERON:0000002 | uterine cervix | 9 | NAT1 |  |  | 0 |  | 0.2 |
| UBERON:0000002 | uterine cervix | 14 | AAMP |  |  | 0 | 0 | 0.5 |
| UBERON:0000002 | uterine cervix | 16 | AARS |  |  | 1 | 1 | 1.7 |
| UBERON:0000002 | uterine cervix | 19 | ABCA1 | 0.6 |  | 0 |  | 0.7 |
| UBERON:0000002 | uterine cervix | 20 | ABCA2 |  |  | 0 |  | 0.5 |
| UBERON:0000002 | uterine cervix | 21 | ABCA3 |  |  | 0 |  | 0.5 |
| UBERON:0000002 | uterine cervix | 22 | ABCB7 |  |  | 0 |  | 0.2 |
| UBERON:0000002 | uterine cervix | 25 | ABL1 | 0.5 |  | 0 |  | 0.8 |

Scores range from 0 to 5 with 5 being the highest level of evidence. Blank values indicate a tissue–gene pair that was not assayed in the corresponding channel.

For more information, see the corresponding [Thinklab discussion](http://thinklab.com/discussion/the-tissues-resource-for-the-tissue-specificity-of-genes/91).

All computation is performed by the [`tissues.ipynb`](tissues.ipynb) notebook. Code was written for Python 3.4.
