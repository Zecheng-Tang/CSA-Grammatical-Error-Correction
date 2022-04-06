# CSA-Grammatical-Error-Correction
This is the instruction for reproduce the score of bert-gec model.

## Environment Setup
Place follow the original [paper](https://github.com/kanekomasahiro/bert-gec) (bert-gec) to setup the environment.


## How to reproduce the results
### Resource
The basic setup and checkpoint are referred to [bert-gec](https://github.com/kanekomasahiro/bert-gec).
One can finetune the model with our **CSA** method on the basis of well-trained [model](https://drive.google.com/drive/folders/1h_r46EswcT1q75qwje6h6yJpOxzAG8gP?usp=sharing). 

`NOTICE`
Before running the command below, one should prepare all the requirements and be familiar with the codes in [bert-gec](https://github.com/kanekomasahiro/bert-gec).

We provide our checkpoints as listing below:
 - [regularization data trained version]()
 - [hard samples trained version]()

### Processing & Training
We process the data on the basis of `fairseq-preprocess`, and train the model with the `fairseq-train` command. We combine the process procedure and finetune procedure of stage 1 in  `finetune.sh` for , and `finetune-wi.sh` script is for Step 2. 

`NOTICE` Before running the scripts, one should set some paths of file (e.g. fairseq dir, subword_nmt, ... ) in the beginning of each script.

One can run the script with `bash` command like:
```
bash finetune.sh /path/to/save_dir /path/to/model_ckp gpu_id /path/to/data
```
### Generating Augmentation Data & Inference
As for these two operation, it shares the same sript `inference.sh`.
One can run the script with `bash` command like:
```
bash inference.sh /path/to/input_file gpu_id /path/to/model_ckp folder_name
```

The inference results are in the ./results/folder_name/test.best.tok

`NOTICE`
For generating augmentation data, we utilize training data as source. 
For inferencing, we utilize testing data as source.

## Results
We have provided all the inference results on four clean datasets in folder ./results






