---
title: Protein-protein Interaction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Protein-Protein Interaction Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Proteins are the fundamental function units of human biology. However, they rarely act alone but usually interact with each other to carry out functions. Protein-protein interactions (PPI) are very important to discover new putative therapeutic targets to cure disease. Expensive and time-consuming wet-lab results are usually required to obtain PPI activity. PPI prediction aims to predict the PPI activity given a pair of proteins' amino acid sequences.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Vast amounts of human PPIs are unknown and untested. Filling in the missing parts of the PPI network can improve human's understanding of diseases and potential disease target. With the aid of an accurate machine learning model, we can greatly facilitate this process. As protein 3D structure is expensive to acquire, prediction based on sequence data is desirable. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
As the majority of PPIs are unknown, the model needs to extrapolate from a given gold-label training set to a diverse of unseen proteins from various tissues and organisms.
</p>

<p class="is-size-6"> <strong> Product: </strong>  Small-molecule, macromolecule.</p>

<p class="is-size-6"> <strong> Pipeline: </strong>  Basic biomedical research, target discovery, macromolecule discovery. </p>

</div>

### HuRI

<p class='is-size-6'>  <strong> Dataset Description: </strong> All pairwise combinations of human protein-coding genes are systematically being interrogated to identify which are involved in binary protein-protein interactions. In the most recent effort 17,500 proteins have been tested and a first human reference interactome (HuRI) map has been generated. From the Center for Cancer Systems Biology at Dana-Farber Cancer Institute. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary Classification. Given the target amino acid sequence pairs, predict if they interact or not. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 51,813 positive PPI pairs, 8,248 proteins </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Drug Split</span> <span class="tag is-info is-light">Cold Protein Split</span> </p>

``` python
from tdc.multi_pred import PPI
data = PPI(name = 'HuRI')
split = data.get_split()
```

<p class="is-size-6"> <strong>Note:</strong> (1) For genes that associate with multiple protein sequences, we separate by * symbol. (2) The dataset contains only positive pairs. All of the unobserved pairs are real negative PPIs, tested experimentally. To get the negative samples, you can call: </p>

```python
data = data.neg_sample(frac = 1)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://doi.org/10.1038/s41586-020-2188-x">[1] Luck, K., Kim, D., Lambourne, L. et al. A reference map of the human binary protein interactome. Nature 580, 402–408 (2020).</a> 

<p class='is-size-6'> <strong> Dataset License: </strong><a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />
