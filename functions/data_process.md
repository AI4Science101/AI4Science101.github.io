---
title: Data Processing
subtitle:
layout: page
toc: true
toc_title: Function Index
show_sidebar: false
menubar: function_menu
hide_hero: true
---

### Molecule Conversion

<p class='is-size-6'>  <strong> Function Description: </strong> Map among ~15 molecular formats. For 2D: currently, we support to map from SMILES/SEFLIES and convert to SELFIES/SMILES, Graph2D, PyG, DGL, ECFP2-6, MACCS, Daylight, RDKit2D, Morgan, PubChem; For 3D: we support to map from XYZ, SDF files to Graph3D, Columb Matrix. To do that, first initialize a convert class and then feed in the input format. The conversion class takes in the following input: </p>

<ul>
	<li><code>src</code>: source molecule format. Choose from SMILES/SELFIES for 2D and SDF/XYZ for 3D. </li>
	<li><code>dst</code>: destination molecule format. For 2D, choose from SMILES/SELFIES/Graph2D/PyG/DGL/ECFP2/ECFP4/ECFP6/MACCS/Daylight/RDKit2D/Morgan/PubChem. For 3D, choose from SMILES/SELFIES/Graph3D/Columb.</li>
</ul>

``` python
from tdc.chem_utils import MolConvert
converter = MolConvert(src = 'SMILES', dst = 'Graph2D')
converter(['Clc1ccccc1C2C(=C(/N/C(=C2/C(=O)OCC)COCCN)C)\C(=O)OC',
       'CCCOc1cc2ncnc(Nc3ccc4ncsc4c3)c2cc1S(=O)(=O)C(C)(C)C'])
```

<p class="is-size-6"> <strong>Note</strong>: to check the eligible destination format for each source type, you can type: </p>

```python
from tdc.chem_utils import MolConvert
MolConvert.eligible_format()
# MolConvert.eligible_format(src = 'SDF') for specific source type
```
<p class="is-size-6"> While for 3D the destination format does not include most of 2D ones, you can also easily convert to any 2D format by: </p>

```python
from tdc.chem_utils import MolConvert
convert = MolConvert(src = 'SDF', dst = 'SMILES')
g = convert('XXX/.sdf')
convert2d = MolConvert(src = 'SMILES', dst = 'ECFP4')
convert2d(g)
```

----

### Molecule Filters

<p class='is-size-6'>  <strong> Function Description: </strong> This function identifies and removes typical not drug-like molecules (false positives) using various types of filters curated by Patrick Walters. This is a wrapper around his <a href="">rd_filters</a> GitHub package. Also checkout his <a href="http://practicalcheminformatics.blogspot.com/2018/08/filtering-chemical-libraries.html">blog post </a>for more info. </p>

<p class='is-size-6'> You can specify the rules for the filters. For example, specify what kinds of structure alerts to use and also the range for some properties: </p>

<ul>
	<li><code>filters</code>: a list of curated rules to use. Choose from any combinations of 'BMS', 'Dundee', 'Glaxo', 'Inpharmatica', 'LINT', 'MLSMR', 'PAINS', 'SureChEMBL'. Default use all rules. </li>
	<li><code>HBA, HBD, LogP, MW, Rot, TPSA</code>: A set of real valued property filters. Default is HBA = [0, 10], HBD = [0, 5], LogP = [-5, 5], MW = [0, 500], Rot = [0, 10], TPSA = [0, 200]. </li>
</ul>

``` python
from tdc.chem_utils import MolFilter
filters = MolFilter(filters = ['PAINS'], HBD = [0, 6])
filters(['CCSc1ccccc1C(=O)Nc1onc2c1CCC2'])
```

----

### Label Distribution Visualization

<p class='is-size-6'>  <strong> Function Description: </strong> This function visualizes the label distribution and prints the basic statistics such as mean and median. </p>

<p class='is-size-6'> For example, to visualize the Caco-2 label distribution: </p>

``` python
from tdc.single_pred import ADME
data = ADME(name = 'Caco2_Wang')
data.label_distribution()
```

----

### Label Binarization

<p class='is-size-6'>  <strong> Function Description: </strong> For labels with real value, it binarizes the label given a threshold. It takes in the following two inputs: </p>

<ul>
	<li><code>threshold</code>: a real value where below/above it is set to be 0/1 depending on the order. This is a required parameter. </li>
	<li><code>order</code>: choose from 'descending' (the larger is 0) or 'ascending' (the smaller is 0). Default is 'descending'. </li>
</ul>

<p class='is-size-6'> For example, we show how to binarize the DAVIS dataset in the DTI task. Since the binding affinity is the lower the better, we want to set values that are below 30 to be 1 and others 0: </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'DAVIS')
data.binarize(threshold = 30, order = 'descending')
```

<p class='is-size-6'> <strong>Note</strong>: you can use <code>data.label_distribution()</code> to visualize the label distribution and decide on the threshold. </p>

----

### Label Units Conversion

<p class='is-size-6'>  <strong> Function Description: </strong> This function converts the labels to different units. Currently, it supports to transform between nM and p (log scale) for binding affinity and also regular natural log the label.  </p>

<p class='is-size-6'> For example, to convert from nM to p: </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'DAVIS')
data.convert_to_log(form = 'binding')
# convert back: data.convert_from_log(form = 'binding')
```

<p class="is-size-6">To convert to natural log scale:</p>

``` python
from tdc.single_pred import ADME
data = ADME(name = 'Caco2_Wang')
data.convert_to_log(form = 'standard')
# convert back: data.convert_from_log(form = 'standard')
```

----

### Label Meaning

<p class='is-size-6'>  <strong> Function Description: </strong> This function maps each labels to meaningful texts explaining what the label represents. Only applies to certain datasets.  </p>

<p class='is-size-6'> For example, to obtain what interaction type between DDIs: </p>

``` python
from tdc.multi_pred import DDI
from tdc.utils import get_label_map
data = DDI(name = 'DrugBank')
get_label_map(name = 'DrugBank', task = 'DDI')
```

----

### Basic Statistics

<p class='is-size-6'>  <strong> Function Description: </strong> This function prints the basic statistics of the dataset, such as number of data points. </p>

``` python
from tdc.multi_pred import GDA
data = GDA(name = 'DisGeNET')
data.print_stats()
```

----

### Data Balancing

<p class='is-size-6'>  <strong> Function Description: </strong> For binary classification, many therapeutics datasets are highly imbalanced. This function either oversamples the minority class or subsample the majority class to create a balanced dataset. It takes in the following two inputs: </p>

<ul>
	<li><code>oversample</code>: this is set to be either true (oversample) or false (subsample). In default, it is set to be false. </li>
	<li><code>seed</code>: the random seed for oversample/subsample. The default is seed 42. </li>
</ul>

<p class='is-size-6'> For example, SARS-CoV2 3CL Protease screening data is highly imbalanced, we want to oversample the positive class: </p>

``` python
from tdc.single_pred import HTS
data = HTS(name = 'SARSCoV2_3CLPro_Diamond')
data.balanced(oversample = True, seed = 42)
```

----

### Graph Transformation for Pair Data

<p class='is-size-6'>  <strong> Function Description: </strong> Many bi-entities prediction task can be formulated as a graph link prediction task. This function constructs the graph from the paired data. </p>

<ul>
	<li><code>threshold</code>: a real value where below/above it is set to be 0/1 depending on the order. Default is None. </li>
	<li><code>format</code>: choose from 'edge_list', 'dgl' (return a DGL graph object), or 'pyg' (return a Pytorch Geometric object). Default is 'edge_list'. </li>
	<li><code>split</code>: choose from True or False. If set to true, also return the random train/val/test edge split as in the data frame format. </li>
	<li><code>frac</code>: if split is True, this specifies the fraction of train/val/test splits. Default is [0.7, 0.1, 0.2]. </li>
	<li><code>seed</code>: the random seed for splitting. The default is 42. </li>
	<li><code>order</code>: choose from 'descending' (the larger is 0) or 'ascending' (the smaller is 0). Default is 'descending'. </li>
</ul>

<p class='is-size-6'> For example, to construct a graph for DTI DAVIS dataset with threshold 30, split set to true, fraction 70%/10%/20%, seed 42, and descending order: </p>

``` python
from tdc.multi_pred import DTI
data = DTI(name = 'DAVIS')
data.to_graph(threshold = 30, format = 'edge_list', split = True, frac = [0.7, 0.1, 0.2], seed = 42, order = 'descending')
# output: {'edge_list': array of shape (X, 2), 'neg_edges': array of shape (X, 2), 'split': {'train': df, 'valid': df, 'test': df}}

data.to_graph(threshold = 30, format = 'dgl', split = True, frac = [0.7, 0.1, 0.2], seed = 42, order = 'descending')
# output: {'dgl_graph': the DGL graph object, 'index_to_entities': a dict map from ID in the data to node ID in the DGL object, 'split': {'train': df, 'valid': df, 'test': df}}

data.to_graph(threshold = 30, format = 'pyg', split = True, frac = [0.7, 0.1, 0.2], seed = 42, order = 'descending')
# output: {'pyg_graph': the PyG graph object, 'index_to_entities': a dict map from ID in the data to node ID in the PyG object, 'split': {'train': df, 'valid': df, 'test': df}}
```

----

### Negative Sampling

<p class='is-size-6'>  <strong> Function Description: </strong> For some interaction datasets, there are only positive samples provided. In order to do binary classification, we have to construct negative samples. One popular way is to consider the unobserved as negative samples. This is usually the case for biomedical data as a hit has way smaller chance than being negative. For some dataset with pairwise experimental assay (e.g. HuRI), sample from the unobserved pair are also true negatives. To do that, it takes in the following input: </p>

<ul>
	<li><code>frac</code>: the percentage of negative samples compared to existing positive ones. In default, it is set to be 1, i.e. balanced. </li>
</ul>

<p class='is-size-6'> For example, HuRI dataset from PPI only consists of positive data points. We can obtain a new dataset with negative samples by: </p>

``` python
from tdc.multi_pred import PPI
data = PPI(name = 'HuRI')
data = data.neg_sample(frac = 1)
```

----

### From PubChem CIDs to SMILES

<p class='is-size-6'>  <strong> Function Description: </strong> Retrieve SMILES string from the PubChem CID. To do that, it takes in the following input: </p>

<ul>
	<li><code>cid</code>: the PubChem CID. </li>
</ul>

<p class='is-size-6'>  <strong> Note: </strong> For large batch of queries, please use the <a href="https://pubchem.ncbi.nlm.nih.gov/idexchange/idexchange.cgi">PubChem ID exchange service</a>. </p>

``` python
from tdc.utils import cid2smiles
smiles = cid2smiles(2248631)
# 'CCOC1=CC(=C(C=C1C=CC(=O)O)Br)OCC'
```

----

### From Uniprot IDs to Amino Acid Sequences

<p class='is-size-6'>  <strong> Function Description: </strong> Retrieve amino acid sequence from the Uniprot ID. To do that, it takes in the following input: </p>

<ul>
	<li><code>id</code>: the Uniprot ID. </li>
</ul>

<p class='is-size-6'>  <strong> Note: </strong> For large batch of queries, please use the <a href="https://www.uniprot.org/uploadlists/">Uniprot ID mapping service</a>. </p>

``` python
from tdc.utils import uniprot2seq
seq = uniprot2seq('P49122')
# 'MKTLLLTLVVVTIVCLDLGYTLKCHNTQLPFIYNTCPEGKNLCFKATLKFPLKFPVKRGCAATCPRSSSLVKVVCCKTDKCN'
```

----