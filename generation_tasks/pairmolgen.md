---
title: Paired Molecule Generation
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: generation_menu
hide_hero: true
---

# Paired Molecule Generation Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Paired molecule generation defines a set of molecule pairs (X,Y), where Y is a paraphrase of X with more desirable chemical property. In other words, the machine learning model aims to translate the input molecule X into a similar molecule Y with better property. 
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Lead optimization is a crucial step in drug discovery and consumes lots of time and trial. After a drug candidate hit is identified via high throughput screening, enhanced similar candidates are created and tested in order to find a lead compound with better properties than the original hit. Paired molecule generation is able to automate and accelerate the process.  
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The generated molecules have to obtain superior properties given a range of structurally diverse drugs. Besides, the generated molecules have to suffice other basic properties, such as synthesizablility and low off-target effects.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety - lead development and optimization. </p>

</div>

### DRD2

<p class='is-size-6'>  <strong> Dataset Description: </strong> DRD2 stands for dopamine type 2 receptor.  The model needs to translate inactive compounds (p < 0.05) into active compounds (p ≥ 0.5), where the bioactivity is assessed by a property prediction model oracle. The dataset is curated from ZINC. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given a molecule X, translate to another molecule Y with higher activity to DRD2. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 34,404 molecule pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import PairMolGen
data = PairMolGen(name = 'DRD2')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://openreview.net/forum?id=rJeeKTNKDB">[1] Jin, Wengong, et al. "Learning multimodal graph-to-graph translation for molecular optimization." ICLR (2019).
</a> 

<a href="https://link.springer.com/article/10.1186/s13321-017-0235-x"> [2] Olivecrona, Marcus, et al. "Molecular de-novo design through deep reinforcement learning." Journal of cheminformatics 9.1 (2017): 48.
</a>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00559"> [3] Sterling, Teague, and John J. Irwin. "ZINC 15–ligand discovery for everyone." Journal of chemical information and modeling 55.11 (2015): 2324-2337.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />

### QED

<p class='is-size-6'>  <strong> Dataset Description: </strong> QED stands for Quantitative Estimate of Drug-likeness. The model needs to translate molecules with QED scores within the range [0.7, 0.8] into the higher range [0.9, 1.0]. The dataset is curated from ZINC. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given a molecule X, translate to another molecule Y with higher QED. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 88,306 molecule pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import PairMolGen
data = PairMolGen(name = 'QED')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://openreview.net/forum?id=rJeeKTNKDB">[1] Jin, Wengong, et al. "Learning multimodal graph-to-graph translation for molecular optimization." ICLR (2019).
</a> 

<a href="https://idp.nature.com/authorize/casa?redirect_uri=https://www.nature.com/nchem/journal/v4/n2/full/nchem.1243.html&casa_token=nRlnIU95a34AAAAA:UKkVVcB_V3z8ZeuWuwSbumNW4YIK-5_Yt49UYOCpSOzB-hETkOxdhLaGzYN2s4_GBDv3laavmqWlGAl5aA"> [2] Bickerton, G. Richard, et al. "Quantifying the chemical beauty of drugs." Nature chemistry 4.2 (2012): 90-98.
</a>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00559"> [3] Sterling, Teague, and John J. Irwin. "ZINC 15–ligand discovery for everyone." Journal of chemical information and modeling 55.11 (2015): 2324-2337.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />

### LogP

<p class='is-size-6'>  <strong> Dataset Description: </strong> The penalized logP score measures the solubility and synthetic accessibility of a compound. In this task, the model needs to translate input X into output Y such that logP(Y) > logP(X). The dataset is curated from ZINC. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> Given a molecule X, translate to another molecule Y with higher LogP. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 99,909 molecule pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import PairMolGen
data = PairMolGen(name = 'LogP')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://openreview.net/forum?id=rJeeKTNKDB">[1] Jin, Wengong, et al. "Learning multimodal graph-to-graph translation for molecular optimization." ICLR (2019).
</a> 

<a href="http://proceedings.mlr.press/v70/kusner17a.html"> [2] Kusner, Matt J., Brooks Paige, and José Miguel Hernández-Lobato. "Grammar variational autoencoder." ICML 2017.
</a>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00559"> [3] Sterling, Teague, and John J. Irwin. "ZINC 15–ligand discovery for everyone." Journal of chemical information and modeling 55.11 (2015): 2324-2337.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />