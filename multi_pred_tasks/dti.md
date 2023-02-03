---
title: Drug-Target Interaction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Drug-Target Interaction Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
The activity of a small-molecule drug is measured by its binding affinity with the target protein. Given a new target protein, the very first step is to screen a set of potential compounds to find their activity. Traditional method to gauge the affinities are through high-throughput screening wet-lab experiments. However, they are very expensive and are thus restricted by their abilities to search over a large set of candidates. Drug-target interaction prediction task aims to predict the interaction activity score in silico given only the accessible compound structural information and protein amino acid sequence. 
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Machine learning models that can accurately predict affinities can not only save pharmaceutical research costs on reducing the amount of high-throughput screening, but also to enlarge the search space and avoid missing potential candidates.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
Models require extrapolation on unseen compounds, unseen proteins, and unseen compound-protein pairs. Models also are expected to have consistent performance across a diverse set of disease and target groups. 
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity - hit identification. </p>

</div>

### BindingDB

<p class='is-size-6'>  <strong> Dataset Description: </strong> BindingDB is a public, web-accessible database of measured binding affinities, focusing chiefly on the interactions of protein considered to be drug-targets with small, drug-like molecules. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the target amino acid sequence/compound SMILES string, predict their binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> (# of DTI pairs, # of drugs, # of proteins) 52,284/10,665/1,413 for Kd, 991,486/549,205/5,078 for IC50, 375,032/174,662/3,070 for Ki. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Drug Split</span> <span class="tag is-info is-light">Cold Protein Split</span> </p>

<p class='is-size-6'>  <strong> Note: </strong> BindingDB is the collection of many assays. Since different assays use different metrics, TDC separates them as separate datasets. Specifically, it has four datasets with Kd, IC50, Ki as the units. </p>

<p class="is-size-6"> <strong>Tips:</strong> Transforming to log-scale pIC50, pKi, and pKd can usually lead to more stable training. You can achieve this transformation via <a href="/functions/data_process/#label-units-conversion">here</a>. Checkout the <a href="/functions/data_process">data processing</a> page for binarization, label distribution visualization, edge list/DGL/PyTorch graph transformation. </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'BindingDB_Kd')
# data = DTI(name = 'BindingDB_IC50')
# data = DTI(name = 'BindingDB_Ki')
split = data.get_split()
```

<p class="is-size-6"><strong>Note:</strong> Many DTI pairs have same sequence information but different binding affinities due to different experimental assays. To harmonize them, you can use the below function to retrieve either the maximum affinity or the mean for the duplicated pair:</p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'BindingDB_Kd')
data.harmonize_affinities(mode = 'max_affinity')
# data.harmonize_affinities(mode = 'mean')
```


<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article-abstract/35/suppl_1/D198/1119109">[1] Liu, Tiqing, et al. "BindingDB: a web-accessible database of experimentally determined protein–ligand binding affinities." Nucleic acids research 35.suppl_1 (2007): D198-D201. </a> 

<a href="https://arxiv.org/abs/2004.08919">[2] Huang, Kexin, et al. "DeepPurpose: a Deep Learning Library for Drug-Target Interaction Prediction" Bioinformatics. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/3.0/us/">CC BY 3.0 US</a>.</p>


<hr />

### DAVIS

<p class='is-size-6'>  <strong> Dataset Description: </strong> The interaction of 72 kinase inhibitors with 442 kinases covering >80% of the human catalytic protein kinome. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the target amino acid sequence/compound SMILES string, predict their binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> <code>0.3.2</code> Update: 25,772 DTI pairs, 68 drugs, 379 proteins. Before: 27,621 DTI pairs, 68 drugs, 379 proteins. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Drug Split</span> <span class="tag is-info is-light">Cold Protein Split</span> </p>

<p class="is-size-6"> <strong>Tips:</strong> Transforming to log-scale pIC50, pKi, and pKd can usually lead to more stable training. You can achieve this transformation via <a href="/functions/data_process/#label-units-conversion">here</a>. Checkout the <a href="/functions/data_process">data processing</a> page for binarization, label distribution visualization, edge list/DGL/PyTorch graph transformation. </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'DAVIS')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.nature.com/articles/nbt.1990">[1] Davis, M., Hunt, J., Herrgard, S. et al. Comprehensive analysis of kinase inhibitor selectivity. Nat Biotechnol 29, 1046–1051 (2011). </a> 

<a href="https://arxiv.org/abs/2004.08919">[2] Huang, Kexin, et al. "DeepPurpose: a Deep Learning Library for Drug-Target Interaction Prediction" Bioinformatics. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### KIBA

<p class='is-size-6'>  <strong> Dataset Description: </strong> Toward making use of the complementary information captured by the various bioactivity types, including IC50, K(i), and K(d), Tang et al. introduces a model-based integration approach, termed KIBA to generate an integrated drug-target bioactivity matrix. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given the target amino acid sequence/compound SMILES string, predict their binding affinity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> <code>0.3.2</code> Update: 117,657 DTI pairs, 2,068 drugs, 229 proteins. Before: 118,036 DTI pairs, 2,068 drugs, 229 proteins. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Cold Drug Split</span> <span class="tag is-info is-light">Cold Protein Split</span> </p>

<p class="is-size-6"> <strong>Tips:</strong> Checkout the <a href="/functions/data_process">data processing</a> page for binarization, label distribution visualization, edge list/DGL/PyTorch graph transformation. </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'KIBA')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/24521231/">[1] Tang J, Szwajda A, Shakyawar S, et al. Making sense of large-scale kinase inhibitor bioactivity data sets: a comparative and integrative analysis. J Chem Inf Model. 2014;54(3):735-743. </a> 

<a href="https://arxiv.org/abs/2004.08919">[2] Huang, Kexin, et al. "DeepPurpose: a Deep Learning Library for Drug-Target Interaction Prediction" Bioinformatics. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />
