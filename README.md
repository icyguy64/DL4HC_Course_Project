Status: Active. Interested readers can contact me at cyl1988@gmail.com


# DL4HC-BERT

Code for my project on NLP for Healthcare titled Prediction of Medical Codes from Clinical Text using Pre-trained Language Model

# Github

Hosted on https://github.com/icyguy64/DL4HC_Course_Project

## Dependencies
* Python 3.8.5 
* pytorch 1.8.1+culll
* tqdm 4.50.2
* scikit-learn 0.23.2
* numpy 1.19.2
* pandas 1.1.3
* jupyter-notebook 
* gensim 4.0.1
* nltk 3.5

Other versions may also work, but the ones listed are the ones I've used


## Data processing

To get started, first edit the notebook entries to point to the directories holding your copies of the MIMIC-II and MIMIC-III datasets. Then, organize your data with the following structure: I have omitted uploading the MIMIC-III dataset to this repository.
```
└───data/
|   NOTEEVENTS.csv
|   DIAGNOSES_ICD.csv
|   PROCEDURES_ICD.csv
```
Now, make sure your python path includes the base directory of this repository. Then, in Jupyter Notebook, run all cells (in the menu, click Cell -> Run All) in  `notebooks/dataproc_mimic_III.ipynb`. These will take some time, so go for a walk or bake some cookies while you wait. You can speed it up by just loading the provided word2vec embeddings and trained models. 

## Saved models

To directly reproduce the results of the paper, first run the ETL and data processing notebooks above. We provide our models for BERT for the MIMIC-III full-label dataset. They are saved as `model_first500only1epoch.bert` in the models directory. We also provide an `evaluate_model.ipynb` notebook to evaluate our model and results from the models.

## Training a new model

To train a new model from scratch, please use the jupyter notebook `notebook/training.ipynb`. The notebook contains all the code necessary to reproduce this work. You'll need to manually edit and confirm the directory you'll be loading from in the notebook (after model training and saving is complete) .

## Model predictions

The predictions that provide the results in the paper are provided in `predictions/`. Each directory contains: 

* `y_hat_0.csv`, which contains the predictions from the first BERT model. 
* `y_all_0.csv`, which contains the actual labels from the first BERT model. 
* `yhat_raws_0.csv`, which contains the raw predictions before rounding from the first BERT model. The number appended behind indicates the index of the BERT model. 0 - First, 500 - Second, 1000 - third, 1500 - fourth, 2000 - fifth

To reproduce our F-measure results from the predictions, for example the CNN results on MIMIC-III datasets, run evalute model notebook. 
