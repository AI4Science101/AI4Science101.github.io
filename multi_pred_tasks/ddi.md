---
title: Drug-Drug Interaction
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: multi_pred_menu
hide_hero: true
---

# Drug-Drug Interaction Prediction Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
	Drug-drug interactions occur when two or more drugs interact with each other. These could result in a range of outcomes from reducing the efficacy of one or both drugs to dangerous side effects such as increased blood pressure or drowsiness. Polypharmacy side-effects are associated with drug pairs (or higher-order drug combinations) and cannot be attributed to either individual drug in the pair. This task is to predict the interaction between two drugs.

</p>

<p class="is-size-6"> <strong> Impact: </strong>  
Increasing co-morbidities with age often results in the prescription of multiple drugs simultaneously. Meta analyses of patient records showed that drug-drug interactions were the cause of admission for prolonged hospital stays in 7% of the cases. Predicting possible drug-drug interactions before they are prescribed is thus an important step in preventing these adverse outcomes. In addition, as the number of combinations or even higher-order drugs is astronomical, wet-lab experiments or real-world evidence are insufficient. Machine learning can provide an alternative way to inform drug interactions.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
As there is a very large space of possible drug-drug interactions that have not been explored, the model needs to extrapolate from known interactions to new drug combinations that have not been prescribed together in the past. Models should also taken into account dosage as that can have a significant impact on the effect of the drugs.
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety - adverse event detection. </p>

</div>

### DrugBank Multi-Typed DDI

<p class='is-size-6'>  <strong> Dataset Description: </strong> DrugBank drug-drug interaction dataset is manually sourced from FDA/Health Canada drug labels as well as primary literature. It has 86 interaction types. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Multi-class classification. Given the SMILES strings of two drugs, predict their interaction type. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 191,808 DDI pairs with 1,706 drugs.  </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import DDI
data = DDI(name = 'DrugBank')
split = data.get_split()
```

<p class='is-size-6'>  <strong> Note: </strong> To know what type of relation the label index corresponds to, use:  </p>

```python
from tdc.utils import get_label_map
get_label_map(name = 'DrugBank', task = 'DDI')
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://academic.oup.com/nar/article/46/D1/D1074/4602867">[1] Wishart DS, et al. (2017) DrugBank 5.0: A major update to the DrugBank database for 2018. Nucleic Acids Res 46:D1074–D1082. </a> 

<a href="https://www.pnas.org/content/115/18/E4304.short"> [2] Ryu, Jae Yong, Hyun Uk Kim, and Sang Yup Lee. "Deep learning improves prediction of drug–drug and drug–food interactions." Proceedings of the National Academy of Sciences 115.18 (2018): E4304-E4311.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> DrugBank Online is offered to the public as a free-to-access resource. Use and re-distribution of the content of DrugBank Online or the DrugBank Data, in whole or in part, for any purpose requires a license. Academic users may apply for a free license for certain use cases and all other users require a paid license. </p>


<hr />

### TWOSIDES Polypharmacy Side Effects

<p class='is-size-6'>  <strong> Dataset Description: </strong> Polypharmacy side-effects are associated with drug pairs (or higher-order drug combinations) and cannot be attributed to either individual drug in the pair (in a drug combination). </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Multi-label classification. Given the SMILES strings of two drugs, predict all side effects. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 4,649,441 DDI pairs with 645 drugs.  </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.multi_pred import DDI
data = DDI(name = 'TWOSIDES')
split = data.get_split()
```

<p class='is-size-6'>  <strong> Note: </strong> To know what type of relation the label index corresponds to, use:  </p>

```python
from tdc.utils import get_label_map
get_label_map(name = 'TWOSIDES', task = 'DDI', name_column = 'Side Effect Name')
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://stm.sciencemag.org/content/4/125/125ra31.short?casa_token=I307jEWdWskAAAAA:B4glz3iI1wW_lYc_bzfSs41xMaHiFHLxOhNhOhW_6Si3lHOKarRIe5s5tHz3S2pY7tcVWB41QP6-47c">[1] Tatonetti, Nicholas P., et al. "Data-driven prediction of drug effects and interactions." Science translational medicine 4.125 (2012): 125ra31-125ra31. </a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />
