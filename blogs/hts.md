---
title: High-throughput Screening
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# High-throughput Screening Prediction Task Overview

<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
High-throughput screening (HTS) is the rapid automated testing of thousands to millions of samples for biological activity at the model organism, cellular, pathway, or molecular level. The assay readout can vary from target binding affinity to fluorescence microscopy of cells treated with drug. HTS can be applied to different kinds of therapeutics however most available data is from testing of small-molecule libraries. In this task, a machine learning model is asked to predict the experimental assay values given a small-molecule compound structure. </p>

<p class="is-size-6"> <strong> Impact: </strong>  
High throughput screening is a critical component of small-molecule drug discovery in both industrial and academic research settings. Increasingly more complex assays are now being automated to gain biological insights on compound activity at a large scale. However, there are still limitations on the time and cost for screening a large library that limit experimental throughput. Machine learning models that can predict experimental outcomes can alleviate these effects and save many times and costs by looking at a larger chemical space and narrowing down a small set of highly likely candidates for further smaller-scale HTS. </p>

<p class="is-size-6"> <strong> Generalization: </strong>  The model should be able to generalize over structurally diverse drugs. It is also important for methods to generalize across cell lines. Drug dosage and measurement time points are also very important factors in determining the efficacy of the drug. </p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity - hit identification. </p>

</div>


### SARS-CoV-2 In Vitro, Touret et al.

<p class='is-size-6'>  <strong> Dataset Description: </strong>  An in-vitro screen of the Prestwick chemical library composed of 1,480 approved drugs in an infected cell-based assay. From MIT AiCures. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict its activity against SARSCoV2. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,480 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import HTS
data = HTS(name = 'SARSCoV2_Vitro_Touret')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.nature.com/articles/s41598-020-70143-6">[1] Touret, F., Gilles, M., Barral, K. et al. In vitro screening of a FDA approved chemical library reveals potential inhibitors of SARS-CoV-2 replication. Sci Rep 10, 13093 (2020).</a> 

<a href="https://www.aicures.mit.edu/data">[2] MIT AI Cures.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong><a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### SARS-CoV-2 3CL Protease, Diamond.

<p class='is-size-6'>  <strong> Dataset Description: </strong> A large XChem crystallographic fragment screen against SARS-CoV-2 main protease at high resolution. From MIT AiCures. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict its activity against SARSCoV2 3CL Protease. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 879 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import HTS
data = HTS(name = 'SARSCoV2_3CLPro_Diamond')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.diamond.ac.uk/covid-19/for-scientists/Main-protease-structure-and-XChem.html">[1] Diamond Light Source </a> 

<a href="https://www.aicures.mit.edu/data">[2] MIT AI Cures.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### HIV

<p class='is-size-6'>  <strong> Dataset Description: </strong> The HIV dataset was introduced by the Drug Therapeutics Program (DTP) AIDS Antiviral Screen, which tested the ability to inhibit HIV replication for over 40,000 compounds. From MoleculeNet. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict its activity against HIV virus. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 41,127 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import HTS
data = HTS(name = 'HIV')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://wiki.nci.nih.gov/display/NCIDTPdata/AIDS+Antiviral+Screen+Data">[1] AIDS Antiviral Screen Data. </a> 

<a href="https://pubs.rsc.org/--/content/articlehtml/2018/sc/c7sc02664a">[2] Wu, Zhenqin, et al. "MoleculeNet: a benchmark for molecular machine learning." Chemical science 9.2 (2018): 513-530.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

