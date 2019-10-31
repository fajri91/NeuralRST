# NeuralRST

This is the reimplementation of Transition-based Neural RST Parsing with Implicit Syntax Features, COLING 2018 (https://www.aclweb.org/anthology/C18-1047/) in Python using Pytorch. The original code can be accessed here: https://github.com/yunan4nlp/NNDisParser and it was implemented in C++ using N3LDG framework.

## Dependencies 
1. Python 2.7
2. Run `pip install -r requirements.txt`

## Data ##
RST Tree Bank.</br>
*https://catalog.ldc.upenn.edu/LDC2002T07*

## External Resource ##
Pretrained word embeddings.</br>
*https://nlp.stanford.edu/projects/glove*</br>

## Implicit Syntax Feature ##
I use the NeuroNLP2. Please refer to https://github.com/fajri91/RSTExtractor to see how I extract it.

## Training ##
Pease run command </br>
`python train_rst_parser.py --batch_size=8 --experiment=exp1 --drop_prob=0.5 --ada_eps=1e-6 --gamma=1e-6 --use_dynamic_oracle=1 --start_dynamic_oracle=20`. 
The example log output is given in folder `experiment`.

With dynamic oracle and syntax feature, we achieve similar result with the original paper: </br>
### Dev Set ###
F1-micro average of: </br>
<pre>
* Span      : 0.8531
* Nucleus   : 0.7236
* Relation  : 0.6017
* Full      : 0.5991
</pre>
### Test Set ###
F1-micro average of: </br>
<pre>
* Span      : 0.8607
* Nucleus   : 0.7251
* Relation  : 0.5949
* Full      : 0.5919
</pre>
