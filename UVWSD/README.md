# UVWSD
This repo is the official implementation of our paper "Vision Meets Definitions: Unsupervised Visual Word Sense Disambiguation Incorporating Gloss Information" accepted in ACL 2023.

# Approach
<img width="1151" alt="Screen Shot 2023-05-28 at 3 39 28 PM" src="https://github.com/soon91jae/UVWSD/assets/9526659/40db64cc-2d72-4308-850d-5c9b624e8f35">

# Usage
First, intsall OpenAI CLIP (https://github.com/openai/CLIP)

    $ conda install --yes -c pytorch pytorch=1.7.1 torchvision cudatoolkit=11
    $ pip install ftfy regex tqdm
    $ pip install git+https://github.com/openai/CLIP.git

Then, download SemEval 2023 task 1 VWSD dataset (https://raganato.github.io/vwsd/).

Note that, the experiments conducted on **train split**

Update the data_path 

data_path = "../Experimental Codes/Dataset/VWSD" # data path

Run the codes

# Mode & model change
You can change modes (GPT_gen, compenstae, wordnet) and CLIP models (ViT-B/32, ViT-L/14)

Modes: 

  wordnet: use WordNet as a dicttionary (WN in the paper)
  
  GPT_gen: use GPT generated definitions

    - Definitions/GPT_Definitions.json (DG in the paper)  
    - Definitions/GPT_Context_Definitions.json (CADG in the paper)
    
  compensate: use GPT generated definitions for OOV cases 
  
    - Definitions/GPT_Definitions.json (WN+DG in the paper)    
    - Definitions/GPT_Context_Definitions.json (WN+CADG in the paper)
    
CLIP_MODEL = "ViT-B/32"

dictionary_type = 'compensate' # GPT_gen (DG or CADG), compensate (WN+DG or WN+CADG), wordnet (WN)


# Citing
    @inproceedings{kwon-etal-2023-vision,
    title = "Vision Meets Definitions: Unsupervised Visual Word Sense Disambiguation Incorporating Gloss Information",
    author = "Kwon, Sunjae  and
      Garodia, Rishabh  and
      Lee, Minhwa  and
      Yang, Zhichao  and
      Yu, Hong",
    booktitle = "Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = jul,
    year = "2023",
    address = "Toronto, Canada",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.acl-long.88",
    pages = "1583--1598"}



