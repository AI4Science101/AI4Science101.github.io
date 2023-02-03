---
title: Retrosynthesis
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: generation_menu
hide_hero: true
---

# Retrosynthesis Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Retrosynthesis is the process of finding a set of reactants that can synthesize a target molecule, i.e., product, which is a fundamental task in drug manufacturing. The target is recursively transformed into simpler precursor molecules until commercially available "starting" molecules are identified. In a data sample, there is only one product molecule, reactants can be one or multiple molecules. Retrosynthesis prediction can be seen as reverse process of Reaction outcome prediction.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Retrosynthesis planning is useful for chemists to design synthetic routes to target molecules. Computational retrosynthetic analysis tools can potentially greatly assist chemists in designing synthetic routes to novel molecules. Machine learning based methods will significantly save the time and cost. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
 The model is expected to accurately generate reactant sets for novel drug candidates with distinct structures from the training set across reaction types with varying reaction conditions.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Manufacturing - Synthesis planning. </p>

</div>

### USPTO-50K

<p class='is-size-6'>  <strong> Dataset Description: </strong> USPTO (United States Patent and Trademark Office)  50K consists of 50K extracted atom-mapped reactions with 10 reaction types. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given the product X, generate the reactant set Y. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 50,036 reactions. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import RetroSyn
data = RetroSyn(name = 'USPTO-50K')
split = data.get_split()
```
<p class='is-size-6'>  <strong> Note: </strong> To get the reaction types of each reaction, you can type: </p>

```python
from tdc.utils import get_reaction_type
get_reaction_type('USPTO-50K')
```
<strong> Note: </strong> Starting `0.3.5`, you can also get the reaction type in the dataframe file in each split by turning on

```python
split = data.get_split(include_reaction_type = True)
```


<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://aspace.repository.cam.ac.uk/handle/1810/244727">[1] Lowe, Daniel Mark. Extraction of chemical structures and reactions from the literature. Diss. University of Cambridge, 2012. </a> 

<a href="https://pubs.acs.org/doi/abs/10.1021/acscentsci.7b00303">[2] Liu, Bowen, et al. "Retrosynthetic reaction prediction using neural sequence-to-sequence models." ACS central science 3.10 (2017): 1103-1113.</a>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.9b00949?casa_token=PwSI4a3S7TkAAAAA:zldJCAJgQjlC2w2yfjUJDZZPD8JwsxnCqYsrnLwv8SaFwrUhjxNt3O358hrA7qq6z_Rh0wa8iTNub4pt"> [3] Zheng, Shuangjia, et al. "Predicting retrosynthetic reactions using self-corrected transformer neural networks." Journal of Chemical Information and Modeling 60.1 (2019): 47-55.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/share-your-work/public-domain/cc0/">CC0</a>.</p>

<hr />

### USPTO

<p class='is-size-6'>  <strong> Dataset Description: </strong> The full USPTO (United States Patent and Trademark Office) retrosynthesis dataset. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given the product X, generate the reactant set Y. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,939,253 reactions. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import RetroSyn
data = RetroSyn(name = 'USPTO')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://figshare.com/articles/Chemical_reactions_from_US_patents_1976-Sep2016_/5104873"> [1]  Daniel Lowe. Chemical reactions from US patents (1976-Sep2016).
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/share-your-work/public-domain/cc0/">CC0</a>.</p>

<hr />
