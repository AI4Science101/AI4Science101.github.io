---
title: Paratope Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Paratope Prediction Task Overview

<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Antibodies, also known as immunoglobulins, are large, Y-shaped proteins that can identify and neutralize a pathogen's unique molecule, usually called an antigen. They play essential roles in the immune system and are powerful tools in research and diagnostics. A paratope, also called an antigen-binding site, is the region that selectively binds the epitope. Although we roughly know the hypervariable regions that are responsible for binding, it is still challenging to pinpoint the interacting amino acids. This task is to predict which amino acids are in the active position of antibody that can bind to the antigen.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Identifying the amino acids at critical positions can accelerate the engineering processes of novel antibodies.

</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The models are expected to be generalized to unseen antibodies with distinct structures and functions.

</p>

<p class="is-size-6"> <strong> Product: </strong> Antibody. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity, efficacy and safety. </p>

</div>

### SAbDab, Liberis et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong> Paratope prediction is to predict the active binding region in the antibody. This dataset is from Parapred, which curates a dataset from SAbDab. It collects both heavy and light chain sequence.  </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Token-level classification. Given an amino acid sequence, predict amino acid token that is active in binding, i.e. X is amino acid sequence, Y is a list of indices for the active positions in X. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,023 antibody chains sequence. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.single_pred import Paratope
data = Paratope(name = 'SAbDab_Liberis')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/bioinformatics/article-abstract/34/17/2944/4972995">[1] Liberis, Edgar, et al. "Parapred: antibody paratope prediction using convolutional and recurrent neural networks." Bioinformatics 34.17 (2018): 2944-2950.
</a> 

<a href="https://academic.oup.com/nar/article-abstract/42/D1/D1140/1044118">[2] Dunbar, James, et al. "SAbDab: the structural antibody database." Nucleic acids research 42.D1 (2014): D1140-D1146.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/3.0/">CC BY 3.0</a>.</p>


<hr />