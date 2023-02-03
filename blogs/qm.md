---
title: Quantum Mechanics
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: single_pred_menu
hide_hero: true
---

# Quantum Mechanics Modeling Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
The motion of molecules and protein targets can be described accurately with quantum theory, i.e., Quantum Mechanics (QM). However, ab initio quantum calculation of many-body system suffers from large computational overhead that is impractical for most applications. Various approximations have been applied to solve energy from electronic structure but all of them have a trade-off between accuracy and computational speed. Machine learning models raise a hope to break this bottleneck by leveraging the knowledge of existing chemical data. This task aims to predict the QM results given a drug's structural information. </p>

<p class="is-size-6"> <strong> Impact: </strong>  
A well-trained model can describe the potential energy surface accurately and quickly, so that more accurate and longer simulation of molecular systems are possible. The result of simulation can reveal the biological processes in molecular level and help study the function of protein targets and drug molecules. </p>

<p class="is-size-6"> <strong> Generalization: </strong> A machine learning model trained on a set of QM calculations require to extrapolate to unseen or structurally diverse set of compounds.  </p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Activity - lead development. </p>

</div>

### QM7b

<p class='is-size-6'>  <strong> Dataset Description: </strong> QM7 is a subset of GDB-13 (a database of nearly 1 billion stable and synthetically accessible organic molecules) composed of all molecules of up to 23 atoms (including 7 heavy atoms C, N, O, and S), where 14 properties (e.g. polarizability, HOMO and LUMO eigenvalues, excitation energies) have to be predicted at different levels of theory (ZINDO, SCS, PBE0, GW). </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given a drug 3D xyz coordinates, predict the drug property. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 7,211 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

<p class='is-size-6'>  <strong> Note: </strong> QM7b contains multiple properties. To retrieve the specific labels for that property, specify the property name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('QM7b')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import QM
data = QM(name = 'QM7b', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/ja902302h">[1] Blum, Lorenz C., and Jean-Louis Reymond. "970 million druglike small molecules for virtual screening in the chemical universe database GDB-13." Journal of the American Chemical Society 131.25 (2009): 8732-8733.</a> 

<a href="https://iopscience.iop.org/article/10.1088/1367-2630/15/9/095003/meta">[2] Montavon, Grégoire, et al. "Machine learning of molecular electronic properties in chemical compound space." New Journal of Physics 15.9 (2013): 095003.</a> 

<p class='is-size-6'> <strong> Dataset License: </strong> Not Specified. <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>

<hr />

### QM8

<p class='is-size-6'>  <strong> Dataset Description: </strong> Electronic spectra and excited state energy of small molecules calculated by multiple quantum mechanic methods. Consisting of low-lying singlet-singlet vertical electronic spectra of over 20 000 synthetically feasible small organic molecules with up to eight CONF atom. From MoleculeNet and loaded from DeepChem. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given a drug 3D xyz coordinates, predict the drug property. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 21,786 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

<p class='is-size-6'>  <strong> Note: </strong> QM8 contains multiple properties. To retrieve the specific labels for that property, specify the property name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('QM8')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import QM
data = QM(name = 'QM8', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/ci300415d">[1] Ruddigkeit, Lars, et al. "Enumeration of 166 billion organic small molecules in the chemical universe database GDB-17." Journal of chemical information and modeling 52.11 (2012): 2864-2875.</a> 

<a href="https://aip.scitation.org/doi/abs/10.1063/1.4928757?casa_token=mVBximpm4AMAAAAA:iG5mbej2eVDthAfXQFx7LIcQ4-b3I9W_5NsUxE_3LjDRHgGzgqJe-LfCmBiPy1W-ZhjO3oB0RXyW">[2] Ramakrishnan, Raghunathan, et al. "Electronic spectra from TDDFT and machine learning in chemical space." The Journal of chemical physics 143.8 (2015): 084111.</a> 

<a href="https://books.google.com/books?hl=en&lr=&id=6OiRDwAAQBAJ&oi=fnd&pg=PT19&dq=deep+learning+for+life+science+Bharath+Ramsundar&ots=SwHP1HB_qK&sig=iox0o4HN7pBkWC-Bw0X1qDNfwwQ">[3] Ramsundar, Bharath, et al. Deep learning for the life sciences: applying deep learning to genomics, microscopy, drug discovery, and more. " O'Reilly Media, Inc.", 2019.</a> 

<a href="https://pubs.rsc.org/--/content/articlehtml/2018/sc/c7sc02664a">[4] Wu, Zhenqin, et al. "MoleculeNet: a benchmark for molecular machine learning." Chemical science 9.2 (2018): 513-530.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />

### QM9

<p class='is-size-6'>  <strong> Dataset Description: </strong> computed geometric, energetic, electronic, and thermodynamic properties for 134k stable small organic molecules made up of CHONF. These molecules correspond to the subset of all 133,885 species with up to nine heavy atoms (CONF) out of the GDB-17 chemical universe of 166 billion organic molecules. We report geometries minimal in energy, corresponding harmonic frequencies, dipole moments, polarizabilities, along with energies, enthalpies, and free energies of atomization. All properties were calculated at the B3LYP/6-31G(2df,p) level of quantum chemistry. From MoleculeNet and loaded from DeepChem. </p>

<p class='is-size-6'>  <strong> Task Description: </strong>Regression. Given a drug 3D xyz coordinates, predict the drug property. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 133,885 drugs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

<p class='is-size-6'>  <strong> Note: </strong> QM8 contains multiple properties. To retrieve the specific labels for that property, specify the property name in the <code>label_name</code> variable to the data loader. You can find all available label names by calling: </p>

```python
from tdc.utils import retrieve_label_name_list
label_list = retrieve_label_name_list('QM9')
```

<p class="is-size-6"> Then, go to the standard TDC data loader procedure with the label name specified. </p>

``` python
from tdc.single_pred import QM
data = QM(name = 'QM9', label_name = label_list[0])
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/ci300415d">[1] Ruddigkeit, Lars, et al. "Enumeration of 166 billion organic small molecules in the chemical universe database GDB-17." Journal of chemical information and modeling 52.11 (2012): 2864-2875.</a> 

<a href="https://aip.scitation.org/doi/abs/10.1063/1.4928757?casa_token=mVBximpm4AMAAAAA:iG5mbej2eVDthAfXQFx7LIcQ4-b3I9W_5NsUxE_3LjDRHgGzgqJe-LfCmBiPy1W-ZhjO3oB0RXyW">[2] Ramakrishnan, Raghunathan, et al. "Electronic spectra from TDDFT and machine learning in chemical space." The Journal of chemical physics 143.8 (2015): 084111.</a> 

<a href="https://books.google.com/books?hl=en&lr=&id=6OiRDwAAQBAJ&oi=fnd&pg=PT19&dq=deep+learning+for+life+science+Bharath+Ramsundar&ots=SwHP1HB_qK&sig=iox0o4HN7pBkWC-Bw0X1qDNfwwQ">[3] Ramsundar, Bharath, et al. Deep learning for the life sciences: applying deep learning to genomics, microscopy, drug discovery, and more. " O'Reilly Media, Inc.", 2019.</a> 

<a href="https://pubs.rsc.org/--/content/articlehtml/2018/sc/c7sc02664a">[4] Wu, Zhenqin, et al. "MoleculeNet: a benchmark for molecular machine learning." Chemical science 9.2 (2018): 513-530.</a>

<p class='is-size-6'> <strong> Dataset License: </strong> <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>.</p>


<hr />