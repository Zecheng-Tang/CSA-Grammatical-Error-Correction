## Get the  adversarial text
This is an instruction for generating attacked sentences , and 1 to 5 vulnerable token of one sentence will be replaced .

## Environment Setup
We use the open source tools NLPAug, so please follow the website (https://github.com/makcedward/nlpaug) to setup the environment.

## Run
Firstly, you should run the following command:
```
cd CSA-Grammatical-Error-Correction/utils/attack/attack_pos
```

One can run the script with `bash` command like:
```
bash attack_pos.sh m2_file gpu
```
We provide a available m2_file in CSA-Grammatical-Error-Correction/utils/attack/temp/m2_file_example , and you can try it.

## Results
You will get the attacked sentences in folder `./result` .
If you want to know where the words in the sentence have been replaced, you can find position files in `./poslist`.