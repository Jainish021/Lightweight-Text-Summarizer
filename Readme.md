# Text Summarization using Knowledge Distillation

## Overview

This project focuses on creating a smaller, faster student text summarization model by distilling knowledge from a larger pre-trained teacher model (PEGASUS). Key aspects include:

- Using the PEGASUS model as the teacher
- Creating a smaller student model with fewer parameters
- Applying knowledge distillation to transfer capabilities of teacher to student
- Training student model on the CNN/DailyMail dataset
- Evaluating models using ROUGE metrics
- Comparing performance and speed of teacher vs student

## Results

- Student model has a size of 1.4 GB and is 2x faster for inference
- Student model achieves comparable ROUGE scores to the teacher:
  - Rouge-1: 39.27
  - Rouge-2: 18.65
  - Rouge-L: 29.06
  - RougeLSum: 35.93

## Installation

The code is implemented in Python, utilizing Hugging Face's Transformers library and TensorFlow. All the dependancies are listed in "requirements.txt" file.

## Dataset Download
Download the dataset from https://www.kaggle.com/datasets/jainishadesara/cnn-dailymail link.
Make a folder named "Data" in your working directory.
Put all the six downloaded data files in "Data" folder.

## Usage

Run the "distillation.py" to download and preprocess the data, to make the student model from teacher model, and finetune the student model to get the Rouge1, Rouge2, Rougel and RougeLSum scores as output in Result/metric.json file.


## Recommended to run on colab

# Guide

To run on colab 

Step 1- Change python version by running the following in a cell and enter(2) to select python 3.8 (or anything less then 3.9) 

!sudo update-alternatives --config python3

Step 2 - Run this

!python --version
!sudo apt install python3-pip

Step 3 - Install Dependencies by running this

!pip install fire <br>
! pip install transformers==4.1.0 <br>
!pip install sentencepiece <br>
!pip install pytorch-lightning==1.0.4 <br>
! pip install datasets <br>
! pip install rouge_score <br>
! pip install GitPython <br>
! pip install rouge_score <br>
! pip install sacrebleu <br>
! pip install protobuf==3.20.* <br>


Step 4 - Change the data_dir variable to give path of you files.

"data_dir": "your path to the data files folder",


Step 5 - Run the distillation.py file by running this 

! python /path/to/your/dir/distillation.py 

## Credits
We used some of the approach from the following repository:
https://github.com/huggingface/transformers/blob/e2c935f5615a3c15ee7439fa8a560edd5f13a457/examples/seq2seq

