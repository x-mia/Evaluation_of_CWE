# Evaluation_of_CWE

## Evaluation and training datasets and script for evaluating cross-lingual embedding models
This repository contains three evaluation datasets for evaluating Estonian-Slovak, Czech-Slovak, and English-Korean language combinations, and training datasets for training Estonian-Slovak and Czech-Slovak (using either [FastText](https://fasttext.cc/) or [SketchEngine](https://embeddings.sketchengine.eu/) pre-trained monolingual word embeddings. Moreover, there is also a script using partially code from [MUSE](https://github.com/facebookresearch/MUSE) [(Conneau et al., 2017)](https://arxiv.org/pdf/1710.04087.pdf). 

### Requirements
* [NumPy](https://numpy.org/)
* [Pandas](https://pandas.pydata.org/)
* [Tqdm](https://tqdm.github.io/)

### Evaluate aligned embeddings
To evaluate aligned embeddings, simply run:
```bash
python eval.py --src_lng SRC_LNG --tgt_lng TGT_LNG --src_path SRC_PATH --tgt_path TGT_PATH --eval_df EVAL_DF --k_num K_NUM --nmax NMAX --output OUTPUT
```
Example:
```bash
python eval.py --src_lng en --tgt_lng ko --src_path vectors-en.txt --tgt_path vectors-ko.txt --eval_df en-ko.csv --k_num 3 --nmax 50000 --output df.csv
```

### References
* Please cite [[1]](https://elex.link/elex2021/wp-content/uploads/2021/08/eLex_2021_06_pp107-120.pdf) if you found the resources in this repository useful.

[1] Denisová, M and Rychlý, P. (2023). [Evaluation of the Cross-lingual Embedding Models from the Lexicographic Perspective.]([https://elex.link/elex2021/wp-content/uploads/2021/08/eLex_2021_06_pp107-120.pdf](https://elex.link/elex2023/)) In Proceedings of the eLex 2023 conference. Lexical Computing CZ, s.r.o. 

```
@Inproceedings{denisova-2021,
  author = "Michaela Denisová and Pavel Rychlý",
  title = "Evaluation of the Cross-lingual Embedding Models from the Lexicographic Perspective",
  booktitle = "Proceedings of the eLex 2023 conference",
  year = "2023",
  publisher = "Lexical Computing CZ, s.r.o."
}
```

### Related work
* [A. Conneau, G. Lample, L. Denoyer, MA. Ranzato, H. Jégou - *Word Translation Without Parallel Data*, 2017](https://arxiv.org/pdf/1710.04087.pdf)
* [E. Grave, P. Bojanowski, P. Gupta, A. Joulin, T. Mikolov - *Learning Word Vectors for 157 Languages*, 2018](https://arxiv.org/abs/1802.06893)
* [O. Herman - *Precomputed Word Embeddings for 15+ Languages*, 2021](https://www.sketchengine.eu/wp-content/uploads/2021-Precomputed-Word-Embeddings.pdf)
