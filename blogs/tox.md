---
title: Toxicity
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Toxicity Prediction Task Overview

<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
Majority of the drugs have some extents of toxicity to the human organisms. This learning task aims to predict accurately various types of toxicity of a drug molecule towards human organisms. 
</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Toxicity is one of the primary causes of compound attrition. Study shows that approximately 70% of all toxicity-related attrition occurs preclinically (i.e., in cells, animals) while they are strongly predictive of toxicities in humans. This suggests that an early but accurate prediction of toxicity can significantly reduce the compound attribution and boost the likelihood of being marketed. 
</p>

<p class="is-size-6"> <strong> Generalization: </strong>  Similar to the ADME prediction, as the drug structures of interest evolve over time, toxicity prediction requires a model to generalize to a set of novel drugs with small structural similarity to the existing drug set.  </p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong>Efficacy and safety - lead development and optimization. </p>

</div>

### Acute Toxicity LD50 

<p class='is-size-6'>  <strong> Dataset Description: </strong> Acute toxicity LD50 measures the most conservative dose that can lead to lethal adverse effects. The higher the dose, the more lethal of a drug. This dataset is kindly provided by the authors of [1]. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given a drug SMILES string, predict its acute toxicity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 7,385 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'LD50_Zhu')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/tx900189p?casa_token=vfBbuxuUCqEAAAAA:YAcI0r4Z3rtlRYP_l5H8OlTfdUh3DVlO6ws_h1NkhpaXH3-NrdI2-s5ghWWJbxfPQw-KhQIAwMi1Di3v">[1] Zhu, Hao, et al. "Quantitative structure− activity relationship modeling of rat acute toxicity by oral exposure." Chemical research in toxicology 22.12 (2009): 1913-1921.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr /> 

### hERG blockers

<p class='is-size-6'>  <strong> Dataset Description: </strong>  Human ether-à-go-go related gene (hERG) is crucial for the coordination of the heart's beating. Thus, if a drug blocks the hERG, it could lead to severe adverse effects. Therefore, reliable prediction of hERG liability in the early stages of drug design is quite important to reduce the risk of cardiotoxicity-related attritions in the later development stages. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict whether it blocks (1) or not blocks (0). </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 648 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'hERG')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.molpharmaceut.6b00471?casa_token=YszQx1sl0QgAAAAA:lIztZjmLzi3CPjnYh4lVFe3FAjOKF12N9IwBxjV4wiGw6S6QbpnegfgHEjwPzbgmpW-Bk9VvY9RLAsVo">[1] Wang, Shuangquan, et al. "ADMET evaluation in drug discovery. 16. Predicting hERG blockers by combining multiple pharmacophores and machine learning approaches." Molecular Pharmaceutics 13.8 (2016): 2855-2866.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />


### hERG Central

<p class='is-size-6'>  <strong> Dataset Description: </strong>  Human ether-à-go-go related gene (hERG) is crucial for the coordination of the heart's beating. Thus, if a drug blocks the hERG, it could lead to severe adverse effects. Therefore, reliable prediction of hERG liability in the early stages of drug design is quite important to reduce the risk of cardiotoxicity-related attritions in the later development stages. There are three targets: hERG_at_1uM, hERG_at_10uM, and hERG_inhib. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> </p>

- hERG_at_1uM: Regression. Given a drug SMILES string, predict the percent inhibition at a 1µM concentration.
- hERG_at_10uM: Regression. Given a drug SMILES string, predict the percent inhibition at a 10µM concentration.
- hERG_inhib: Binary classification. Given a drug SMILES string, predict whether it blocks (1) or not blocks (0). This is equivalent to whether hERG_at_10uM < -50, i.e. whether the compound has an IC50 of less than 10µM.

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 306,893 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

<p class='is-size-6'>  <strong> Note: </strong> Tox21 contains multiple assays data. To retrieve the specific labels for that assay, specify the label name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('herg_central')
```
<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'herg_central', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/22149888/">[1] Du F, Yu H, Zou B, Babcock J, Long S, Li M. hERGCentral: a large database to store, retrieve, and analyze compound-human Ether-à-go-go related gene channel interactions to facilitate cardiotoxicity assessment in drug development. Assay Drug Dev Technol. 2011 Dec;9(6):580-8. doi: 10.1089/adt.2011.0425.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<p class='is-size-6'> <strong> Contributed by: </strong> <a href="https://bbirnbaum.com">Ben Birnbaum</a>.</p>

<hr />

### Ames Mutagenicity

<p class='is-size-6'>  <strong> Dataset Description: </strong> Mutagenicity means the ability of a drug to induce genetic alterations. Drugs that can cause damage to the DNA can result in cell death or other severe adverse effects. Nowadays, the most widely used assay for testing the mutagenicity of compounds is the Ames experiment which was invented by a professor named Ames. The Ames test is a short-term bacterial reverse mutation assay detecting a large number of compounds which can induce genetic damage and frameshift mutations. The dataset is aggregated from four papers. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict whether it is mutagenic (1) or not mutagenic (0). </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 7,255 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'AMES')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/ci300400a?casa_token=A86ksblef0kAAAAA:2kLxP4j2NOigeBsSqUb8C9ThZLVBR_Ztc8gJg_HhyLCRtZF-MfMMyq4bIwhMlH0MyJXZuWkFXXrGqiMR">[1] Xu, Congying, et al. "In silico prediction of chemical Ames mutagenicity." Journal of chemical information and modeling 52.11 (2012): 2840-2847.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />


### DILI (Drug Induced Liver Injury) 

<p class='is-size-6'>  <strong> Dataset Description: </strong>  Drug-induced liver injury (DILI) is fatal liver disease caused by drugs and it has been the single most frequent cause of safety-related drug marketing withdrawals for the past 50 years (e.g. iproniazid, ticrynafen, benoxaprofen). This dataset is aggregated from U.S. FDA’s National Center for Toxicological Research. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict whether it can cause liver injury (1) or not (0). </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 475 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'DILI')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.5b00238">[1] Xu, Youjun, et al. "Deep learning for drug-induced liver injury." Journal of chemical information and modeling 55.10 (2015): 2085-2093.
</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr /> 

### Skin Reaction 

<p class='is-size-6'>  <strong> Dataset Description: </strong> Repetitive exposure to a chemical agent can induce an immune reaction in inherently susceptible individuals that leads to skin sensitization. The dataset used in this study was retrieved from the ICCVAM (Interagency Coordinating Committee on the Validation of Alternative Methods) report on the rLLNA. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict whether it can cause skin reaction (1) or not (0). </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 404 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'Skin Reaction')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.sciencedirect.com/science/article/pii/S0041008X14004529?casa_token=gMz283g8Tj0AAAAA:DNKlQvZC2fUfMNz4vbqB7WEQGSDMpibtoST_G8vhZ7I4GK950VKxrLTK3jBrSlYKH5flC4sJ6O4">[1] Alves, Vinicius M., et al. "Predicting chemically-induced skin reactions. Part I: QSAR models of skin sensitization and their application to identify potentially hazardous compounds." Toxicology and applied pharmacology 284.2 (2015): 262-272.
</a> 

<a href="https://ntp.niehs.nih.gov/whatwestudy/niceatm/test-method-evaluations/immunotoxicity/llna/index.html"> [2] The reduced murine local lymph node assay: an alternative test method using fewer animals to assess the allergic contact dermatitis potential of chemicals and products. </a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr /> 

### Carcinogens

<p class='is-size-6'>  <strong> Dataset Description: </strong> A carcinogen is any substance, radionuclide, or radiation that promotes carcinogenesis, the formation of cancer. This may be due to the ability to damage the genome or to the disruption of cellular metabolic processes.  </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict whether it can cause carcinogen. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 278 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'Carcinogens_Lagunin')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://onlinelibrary.wiley.com/doi/abs/10.1002/qsar.200860192?casa_token=NR55Na01l8gAAAAA:603Kr5drd-EIWlXFQVJpnpEm05-GxMBwVeBJiORBah8IIsPt1yvy8UNdADagv1ty8SlPvX4XF4r7QpWK">[1] Lagunin, Alexey, et al. "Computer‐aided prediction of rodent carcinogenicity by PASS and CISOC‐PSCT." QSAR & Combinatorial Science 28.8 (2009): 806-810.
</a> 

<a href="https://pubs.acs.org/doi/abs/10.1021/ci300367a?casa_token=9fEKYcMw5zoAAAAA:ZDPZ-e-M9RulemgBjAPNkSnWXlVCcPzkxNK9bX40Abz9o24NpitsXY0tizgDL5ekPiNtEPFSeOwwUTHG">[2] Cheng, Feixiong, et al. "admetSAR: a comprehensive source and free tool for assessment of chemical ADMET properties." (2012): 3099-3105.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr /> 


### Tox21

<p class='is-size-6'>  <strong> Dataset Description: </strong> Tox21 is a data challenge which contains qualitative toxicity measurements for 7,831 compounds on 12 different targets, such as nuclear receptors and stree response pathways. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict the toxicity in a specific assay. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> Depends on various assays ~6,000 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

<p class='is-size-6'>  <strong> Note: </strong> Tox21 contains multiple assays data. To retrieve the specific labels for that assay, specify the label name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('Tox21')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'Tox21', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://www.frontiersin.org/research-topics/2954/tox21-challenge-to-build-predictive-models-of-nuclear-receptor-and-stress-response-pathways-as-media">[1] Tox21 Challenge.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### ToxCast

<p class='is-size-6'>  <strong> Dataset Description: </strong> ToxCast includes qualitative results of over 600 experiments on 8k compounds. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict the toxicity in a specific assay. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> Depends on various assays from couple hundres to thousands of drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

<p class='is-size-6'>  <strong> Note: </strong> ToxCast contains multiple assays data. To retrieve the specific labels for that assay, specify the label name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('Toxcast')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'ToxCast', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/27367298/">[1] Richard, Ann M., et al. "ToxCast chemical landscape: paving the road to 21st century toxicology." Chemical research in toxicology 29.8 (2016): 1225-1251.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### ClinTox

<p class='is-size-6'>  <strong> Dataset Description: </strong> The ClinTox dataset includes drugs that have failed clinical trials for toxicity reasons and also drugs that are associated with successful trials. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Binary classification. Given a drug SMILES string, predict the clinical toxicity. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 1,484 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> <span class="tag is-info is-light">Scaffold Split</span>  </p>

``` python
from tdc.single_pred import Tox
data = Tox(name = 'ClinTox')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/27642066/">[1] Gayvert, Kaitlyn M., Neel S. Madhukar, and Olivier Elemento. "A data-driven approach to predicting successes and failures of clinical trials." Cell chemical biology 23.10 (2016): 1294-1301.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />