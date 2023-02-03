---
title: Molecule Generation
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: generation_menu
hide_hero: true
---

# Molecule Generation Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
 Molecule Generation is to generate diverse, novel molecules that has desirable chemical properties. These properties are measured by oracle functions. A machine learning task first learns the molecular characteristics from a large set of molecules where each is evaluated through the oracles. Then, from the learned distribution, we can obtain novel candidates.
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
As the entire chemical space is far too large to screen for each target, high through screening can only be restricted to a set of existing molecule library. Many novel drug candidates are thus usually omitted. A machine learning that can generate novel molecule obeying some pre-defined optimal properties can circumvent this problem and obtain novel class of candidates.

</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The generated molecules have to obtain superior properties given a range of structurally diverse drugs. Besides, the generated molecules have to suffice other basic properties, such as synthesizablility and low off-target effects.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety - lead development and optimization, activity - hit identification. </p>

</div>


### MOSES

<p class='is-size-6'>  <strong> Dataset Description: </strong> Molecular Sets (MOSES) is a benchmark platform for distribution learning based molecule generation. Within this benchmark, MOSES provides a cleaned dataset of molecules that are ideal of optimization. It is processed from the ZINC Clean Leads dataset. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> For both distribution learning-based and goal-oriented molecule generation. That is to generate new molecules that has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> Please visit the <a href="/TDC/functions/oracles"> this page </a> for various goal-oriented learning oracles calculations and <a href="/TDC/functions/data_evaluation/#molecule-generation-metrics">this page</a> for distribution learning metrics. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,936,962 molecules. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import MolGen
data = MolGen(name = 'MOSES')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://arxiv.org/abs/1811.12823">[1] Polykovskiy et al. "Molecular Sets (MOSES): A Benchmarking Platform for Molecular Generation Models.", Frontiers in Pharmacology. (2020). </a> 

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00559"> [2] Sterling, Teague, and John J. Irwin. "ZINC 15–ligand discovery for everyone." Journal of chemical information and modeling 55.11 (2015): 2324-2337.
</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>.</p>

<hr />


### ZINC

<p class='is-size-6'>  <strong> Dataset Description: </strong> ZINC is a free database of commercially-available compounds for virtual screening. It contains over 230 million purchasable compounds in ready-to-dock, 3D formats. TDC uses a 250,000 sampled version from the original Mol-VAE paper. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> For both distribution learning-based and goal-oriented molecule generation. That is to generate new molecules that has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> Please visit the <a href="/TDC/functions/oracles"> this page </a> for various goal-oriented learning oracles calculations and <a href="/TDC/functions/data_evaluation/#molecule-generation-metrics">this page</a> for distribution learning metrics. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 249,455 molecules. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import MolGen
data = MolGen(name = 'ZINC')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00559"> [1] Sterling, Teague, and John J. Irwin. "ZINC 15–ligand discovery for everyone." Journal of chemical information and modeling 55.11 (2015): 2324-2337.
</a>

<a href="https://pubs.acs.org/doi/abs/10.1021/acscentsci.7b00572">[2] Gómez-Bombarelli, Rafael, et al. "Automatic chemical design using a data-driven continuous representation of molecules." ACS central science 4.2 (2018): 268-276.
 </a> 

 <p class='is-size-6'> <strong> Dataset License: </strong> ZINC is free to use for everyone. Redistribution of significant subsets requires written permission from the authors.</p>

<hr />

### ChEMBL

<p class='is-size-6'>  <strong> Dataset Description: </strong> ChEMBL is a manually curated database of bioactive molecules with drug-like properties. It brings together chemical, bioactivity and genomic data to aid the translation of genomic information into effective new drugs. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> For both distribution learning-based and goal-oriented molecule generation. That is to generate new molecules that has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> Please visit the <a href="/TDC/functions/oracles"> this page </a> for various goal-oriented learning oracles calculations and <a href="/TDC/functions/data_evaluation/#molecule-generation-metrics">this page</a> for distribution learning metrics. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,961,462 molecules. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import MolGen
data = MolGen(name = 'ChEMBL')
split = data.get_split()
```

<p class='is-size-6'>  <strong> Note: </strong> Starting <code>0.3.5</code>, ChEMBL-29 version is also available. It has 2084723 compounds. You can retrieve it by calling: </p>

``` python
from tdc.generation import MolGen
data = MolGen(name = 'ChEMBL_V29')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/47/D1/D930/5162468"> [1] Mendez, David, et al. "ChEMBL: towards direct deposition of bioassay data." Nucleic acids research 47.D1 (2019): D930-D940.
</a>

<a href="https://academic.oup.com/nar/article-abstract/43/W1/W612/2467881">[2] Davies, Mark, et al. "ChEMBL web services: streamlining access to drug discovery data and utilities." Nucleic acids research 43.W1 (2015): W612-W620.
 </a> 

 <p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by-sa/3.0/">CC BY-SA 3.0</a>.</p>


<hr />