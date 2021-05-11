This directory contains the jupyter notebooks used for this project.

preprocessing - ETL only the top-50 medical codes and text-preprocessing,
model_train - Model training and evaluation for LR/CNN/BiGRU/CAML,
model_train_BERT - Proposed BERT model training and evaluation
post_process_results - This notebook contains code to obtain the upper performance limits of the proposed model. What is the best F1 score/precision@k this proposed model can obtain? This notebook answers this.

So what I have done is work on the project with two separate notebooks one for LR/CNN/GRU/CAML where I mainly made use of James Mullenbach's code, I tried implementing some of the pipelines such as the ETL and text-preprocessing portions and there were many issues faced such as having to change the input formats to the one the models are looking for. Another notebook where I made use of a pre-trained BERT model and fine-tune it with the MIMIC-III dataset. I have split this 2 notebooks into this 3 different notebooks for ease of reading and organization. 
