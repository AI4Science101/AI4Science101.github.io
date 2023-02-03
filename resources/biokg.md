---
title: BioKG
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: resource_menu
hide_hero: true
---

### HetioNet

<p class='is-size-6'>  <strong> Dataset Description: </strong> Hetionet is an integrative network of biomedical knowledge assembled from 29 different databases of genes, compounds, diseases, and more. The network combines over 50 years of biomedical information into a single resource. In the dataset, TDC processes into a list of triplets where each row contains source_type, source_id, target_type, target_id, relation type, and direction of the relation.</p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong>  47,031 nodes (11 types) and 2,250,197 relationships (24 types). </p>

``` python
from tdc.resource import BioKG
data = BioKG(name = 'HetioNet')
data.get_data()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://elifesciences.org/articles/26726">[1] Himmelstein, Daniel Scott, et al. "Systematic integration of biomedical knowledge prioritizes drugs for repurposing." Elife 6 (2017): e26726.
</a> 

<a href="https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004259"> [2] Himmelstein, Daniel S., and Sergio E. Baranzini. "Heterogeneous network edge prediction: a data integration approach to prioritize disease-associated genes." PLoS Comput Biol 11.7 (2015): e1004259.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />
