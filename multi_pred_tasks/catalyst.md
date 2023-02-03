---
title: Catalyst Prediction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Catalyst Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
During chemical reaction, catalyst is able to increase the rate of the reaction. Catalysts are not consumed in the catalyzed reaction but can act repeatedly. This learning task aims to predict the catalyst for a reaction given both reactant molecules and product molecules.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Conventionally, chemists design and synthesize catalysts by trial and error with chemical intuition, which is usually time-consuming and costly. Machine learning model and automate and accelerate the process, understand the catalytic mechanism, and providing an insight into novel catalytic design. 

</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
In real-world discovery, as discussed, the molecule structures in reaction of interest evolve over time. We expect model to generalize to the unseen molecules and reaction. 
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Manufacturing - synthesis planning.</p>

</div>

### USPTO

<p class='is-size-6'>  <strong> Dataset Description: </strong> USPTO (United States Patent and Trademark Office)  50K consists of 50K extracted atom-mapped reactions with 10 reaction types. TDC selects the most common catalysts that have occurences higher than 100 times. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given reactant and product set X, predict the catalyst Y from a set of most common catalysts. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 721,799 reactions, 712,757 reactants and 702,940 products with 888 common catalyst types. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import Catalyst
data = Catalyst(name = 'USPTO_Catalyst')
split = data.get_split()
```

<p class='is-size-6'>  <strong> Note: </strong> To know what type of catalyst the label index corresponds to, use:  </p>

```python
from tdc.utils import get_label_map
get_label_map(name = 'USPTO_Catalyst', task = 'Catalyst')
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://aspace.repository.cam.ac.uk/handle/1810/244727">[1] Lowe, Daniel Mark. Extraction of chemical structures and reactions from the literature. Diss. University of Cambridge, 2012. </a> 

<a href="https://pubs.acs.org/doi/abs/10.1021/acscentsci.8b00357">[2] Gao, Hanyu, et al. "Using machine learning to predict suitable conditions for organic reactions." ACS central science 4.11 (2018): 1465-1476. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/share-your-work/public-domain/cc0/">CC0</a>.</p>
<hr />