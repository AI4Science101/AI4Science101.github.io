---
title: Epitope Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Epitope Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
An epitope, also known as antigenic determinant, is the region of a pathogen that can be recognized by antibody and cause adaptive immune response. This task is to classify the active and non-active sites from the antigen protein sequences.

</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Identifying the potential epitope is of primary importance in many clinical and biotechnologies, such as vaccine design and antibody development, and for our general understanding of the immune system.

</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The models are expected to be generalized to unseen pathogens antigens amino acid sequences with diverse set of structures and functions.

</p>

<p class="is-size-6"> <strong> Product: </strong> Immunotherapy. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Target discovery. </p>

</div>

### IEDB, Jespersen et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Epitope prediction is to predict the active region in the antigen. This dataset is from Bepipred, which curates a dataset from IEDB. It collects B-cell epitopes and non-epitope amino acids determined from crystal structures.  </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Token-level classification. Given an amino acid sequence, predict amino acid token that is active in binding, i.e. X is amino acid sequence, Y is a list of indices for the active positions in X. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 3,159 antigens. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Epitope
data = Epitope(name = 'IEDB_Jespersen')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/47/D1/D339/5144151">[1] Vita, Randi, et al. "The immune epitope database (IEDB): 2018 update." Nucleic acids research 47.D1 (2019): D339-D343.</a> 

<a href="https://pubmed.ncbi.nlm.nih.gov/28472356/">[2] Jespersen, Martin Closter, et al. "BepiPred-2.0: improving sequence-based B-cell epitope prediction using conformational epitopes." Nucleic acids research 45.W1 (2017): W24-W29.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong>  <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />

### PDB, Jespersen et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Epitope prediction is to predict the active region in the antigen. This dataset is from Bepipred, which curates a dataset from PDB. It collects B-cell epitopes and non-epitope amino acids determined from crystal structures.  </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Token-level classification. Given the antigen's amino acid sequence, predict amino acid token that is active in binding, i.e. X is an amino acid sequence, Y is a list of indices for the active tokens in X. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 447 antigens. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Epitope
data = Epitope(name = 'PDB_Jespersen')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/28472356/">[1] Jespersen, Martin Closter, et al. "BepiPred-2.0: improving sequence-based B-cell epitope prediction using conformational epitopes." Nucleic acids research 45.W1 (2017): W24-W29.</a> 

<a href="https://academic.oup.com/nar/article-abstract/28/1/235/2384399">[2] Berman, Helen M., et al. "The protein data bank." Nucleic acids research 28.1 (2000): 235-242.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong>  <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />