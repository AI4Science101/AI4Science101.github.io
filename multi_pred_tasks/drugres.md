---
title: Drug Response Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Drug Response Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
The same drug compound could have various levels of responses in different patients. To design drug for individual or a group with certain characteristics is the central goal of precision medicine. For example, the same anti-cancer drug could have various responses to different cancer cell lines. This task aims to predict the drug response rate given a pair of drug and the cell line genomics profile.  
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
 The combinations of available drugs and all types of cell line genomics profiles are very large while to test each combination in the wet lab is prohibitively expensive. A machine learning model that can accurately predict a drug's response given various cell lines in silico can thus make the combination search feasible and greatly reduce the burdens on experiments. The fast prediction speed also allows us to screen a large set of drugs to circumvent the potential missing potent drugs. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
A model trained on existing drug cell-line pair should be able to predict accurately on new set of drugs and cell-lines. This requires a model to learn the biochemical knowledge instead of memorizing the training pairs.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity. </p>

</div>

### GDSC1

<p class='is-size-6'>  <strong> Dataset Description: </strong> Genomics in Drug Sensitivity in Cancer (GDSC) is a resource for therapeutic biomarker discovery in cancer cells. It contains wet lab IC50 for 100s of drugs in 1000 cancer cell lines. In this dataset, we use RMD normalized gene expression for cancer lines and SMILES for drugs. Y is the log normalized IC50. This is the version 1 of GDSC. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the gene expression of cell lines and the SMILES of drug, predict the drug sensitivity level. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 177,310 pairs, 958 cancer cells and 208 drugs </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import DrugRes
data = DrugRes(name = 'GDSC1')
split = data.get_split()
```

<p class="is-size-6"> To get the gene names for expressions of cell lines, you can use: </p>

```python
data.get_gene_symbols()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/41/D1/D955/1059448">[1] Yang, Wanjuan, et al. "Genomics of Drug Sensitivity in Cancer (GDSC): a resource for therapeutic biomarker discovery in cancer cells." Nucleic acids research 41.D1 (2012): D955-D961. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by-nc-nd/2.5/">CC BY-NC-ND 2.5</a>.</p>


<hr />

### GDSC2

<p class='is-size-6'>  <strong> Dataset Description: </strong> Genomics in Drug Sensitivity in Cancer (GDSC) is a resource for therapeutic biomarker discovery in cancer cells. It contains wet lab IC50 for 100s of drugs in 1000 cancer cell lines. In this dataset, we use RMD normalized gene expression for cancer lines and SMILES for drugs. Y is the log normalized IC50. This is the version 2 of GDSC, which uses improved experimental procedures. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the gene expression of cell lines and the SMILES of drug, predict the drug sensitivity level. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 92,703 pairs, 805 cancer cells and 137 drugs </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import DrugRes
data = DrugRes(name = 'GDSC2')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/41/D1/D955/1059448">[1] Yang, Wanjuan, et al. "Genomics of Drug Sensitivity in Cancer (GDSC): a resource for therapeutic biomarker discovery in cancer cells." Nucleic acids research 41.D1 (2012): D955-D961. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by-nc-nd/2.5/">CC BY-NC-ND 2.5</a>.</p>

<hr />

