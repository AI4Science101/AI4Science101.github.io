---
title: Structure-based Drug Design
subtitle: 
toc: true
toc_title: Dataset Index
layout: page
show_sidebar: false
menubar: generation_menu
hide_hero: true
---

# Structure-based Drug Design Task Overview


<div class="box">
	

<p class='is-size-6'>  <strong> Definition: </strong> 
 Structure-based Drug Design is to generate diverse, novel molecules that have high binding affinity to protein pockets (3D structures) and desirable chemical properties. These properties are measured by oracle functions. A machine learning task first learns the molecular characteristics given specific protein pockets from a large set of protein-ligand pair data. Then, from the learned conditional distribution, we can sample novel candidates.</p>

<p class="is-size-6"> <strong> Impact: </strong>  
 Designing a new drug candidate taking account into its structure and potential interaction with biological targets is of great importance to drug design (often referred as to structure-based drug design). Recent advances in machine learning, especially geometric deep learning have brought a new set of tools and a new wave for modeling highly structural data (including 3D biomolecular structures). Thus, structure-based drug design task is potentially of interest to both ML methodological advancements and applications in drug design.
</p>

<p class="is-size-6"> <strong> Generalization: </strong> 
The generated molecules have to obtain superior properties given a range of high binding affinity, and structurally diverse drugs. Besides, the generated molecules have to suffice other basic properties, such as synthesizablility and drug-likeness. 
</p>

<p class="is-size-6"> <strong> Product: </strong> Small-molecule. </p>

<p class="is-size-6"> <strong> Pipeline: </strong> Efficacy and safety - lead development and optimization, activity - hit identification. </p>

</div>


### PDBBind

<p class='is-size-6'>  <strong> Dataset Description: </strong> PDBBind is a comprehensive database extracted from PDB with experimentally measured binding affinity data for protein-ligand complexes. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> SBDD is to generate ligand that binds to protein pocket and has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> : PDBBind does not allow re-distribution of the dataset in any format, thus, we could not host it in TDC server. However, since it requires significant processing to make the dataset ML ready, we provide an alternative route to do it. The user only needs to register in <a href="http://www.pdbbind.org.cn/"> http://www.pdbbind.org.cn/ </a> and download the raw dataset, and then provide the local path, TDC will then automatically detect the path and transform it to ML-ready format into the TDC dataloader.
 </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 19,445 protein-ligand pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import SBDD
data = SBDD(name='PDBBind', path='./pdbbind')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="http://pubs.acs.org/doi/abs/10.1021/jm030580l">[1] Wang, Renxiao, Xueliang Fang, Yipin Lu, and Shaomeng Wang. "The PDBbind database: Collection of binding affinities for protein−ligand complexes with known three-dimensional structures." Journal of medicinal chemistry 47, no. 12 (2004): 2977-2980.  </a> 


<p class='is-size-6'> <strong> Dataset License: </strong> See note above.</p>

<hr />



### DUD-E

<p class='is-size-6'>  <strong> Dataset Description: </strong> DUD-E provides a directory of useful decoys for protein-ligand docking. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> SBDD is to generate ligand that binds to protein pocket and has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> : DUD-E does not support pocket extraction as protein and ligand are not aligned.</p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 22,886 active compounds and affinities against 102 targets </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import SBDD
data = SBDD(name='dude')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/10.1021/jm300687e">[1] Mysinger, M.M., Carchia, M., Irwin, J.J. and Shoichet, B.K., 2012. Directory of useful decoys, enhanced (DUD-E): better ligands and decoys for better benchmarking. Journal of medicinal chemistry, 55(14), pp.6582-6594.  </a> 


<p class='is-size-6'> <strong> Dataset License: </strong> Not specified.</p>

<hr />


### scPDB

<p class='is-size-6'>  <strong> Dataset Description: </strong>  scPDB is processed from PDB for structure-based drug design that identifies suitable binding site for protein-ligand docking. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> SBDD is to generate ligand that binds to protein pocket and has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 16,034 protein-ligand pairs over 4,782 proteins and 6,326 ligands </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import SBDD
data = SBDD(name='scPDB')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/21398668/">[1]Meslamani, J., Rognan, D. and Kellenberger, E., 2011. sc-PDB: a database for identifying variations and multiplicity of ‘druggable’ binding sites in proteins. Bioinformatics, 27(9), pp.1324-1326.  </a> 


<p class='is-size-6'> <strong> Dataset License: </strong> Not specified.</p>

<hr />

<!--
### CrossDock

<p class='is-size-6'>  <strong> Dataset Description: </strong>   CrossDock provides binding poses of ligands docked into binding pockets across PDB. </p>

<p class='is-size-6'>  <strong> Task Description: </strong> SBDD is to generate ligand that binds to protein pocket and has desirable properties measured by some oracles. </p>

<p class='is-size-6'>  <strong> Note: </strong> : The subset of crossdock [1] is provided by [2]. </p>


<p class='is-size-6'>  <strong> Dataset Statistics: </strong> 184,057 protein-ligand pairs. </p>

<p class='is-size-6'>  <strong> Dataset Split: </strong> <span class="tag is-info is-light">Random Split</span> </p>

``` python
from tdc.generation import SBDD
data = SBDD(name='crossdock')
split = data.get_split()
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubmed.ncbi.nlm.nih.gov/32865404/">[1]Francoeur, P.G., Masuda, T., Sunseri, J., Jia, A., Iovanisci, R.B., Snyder, I. and Koes, D.R., 2020. Three-dimensional convolutional neural networks and a cross-docked data set for structure-based drug design. Journal of chemical information and modeling, 60(9), pp.4200-4215. </a> 

<a href="https://openreview.net/forum?id=yDwfVD_odRo">[2] Luo, S., Guan, J., Ma, J. and Peng, J., 2022. A 3D Molecule Generative Model for Structure-Based Drug Design. arXiv preprint arXiv:2203.10446.
License: Not specified.
 </a> 


<p class='is-size-6'> <strong> Dataset License: </strong> Not specified.</p>

<hr />

-->