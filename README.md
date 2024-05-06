This repo contains all the source used for the Final Project - Stop Hate Coalition 

**Authors**: Chujun Chen, Sicheng Yang, Yijia Xue

**Introduction**: In the modern era, characterized by a vast increase in social media use and online forums, there is a corresponding rise in the visibility of hate speech. This trend poses significant risks, particularly to minority groups, by potentially inciting societal polarization and real-life crimes. To help with creating an inclusive and friendly online communication environment, our project aims to identify one effective model for classifying and detecting hate speech by evaluating various deep learning models – DistillBERT, LSTM, BiLSTM, CNN-LSTM – through both qualitative (visualizations) and quantitative (performance metrics) measures. 
Numerous studies have explored the use of deep neural networks for detecting hate speech on social media. Yet, most of these models function as ‘black boxes’, obscuring their internal decision-making processes from users. Our project addresses this issue by enhancing the interpretability of these models, offering a transparent, visual representation of the decision-making process, particularly in identifying sentiments and classifying texts with hateful or extremist content.


## Repo Intro

The project is built in Python 3.9.13 and repository organization is as follows:

*** Project Directory Structure ***

- `data/`
  - Stores all raw and preprocessed data files.

- `figures/`
  - Stores all visualizations(Confusion matrix).

- `stats_results/`
  - Contains the detailed output result for each model.


- `src/`
  - Contains all the code:
    - `evaluation`: contains test_save_stats.py which arrange all the output put result in a csv
    - `training`: contains all the model architecture and code for the training and testing phase, it also contains the code for qualitative result visualization


## Environment and Required Packages
The requirement is stated in the environment.yml file. You can now use this file to create a conda environment with all the necessary packages by running: conda env create -f environment.yml

## Training Phase

### Start training | Default to BasicLSTM
python -m src.training.main
The hyper parameter, model types and arguments are listed in the main.py in the training folder

### Testing Phase
### Example on our best BasicLSTM trained model
python -m src.evaluation.test_save_stats --model BasicLSTM --saved_model_path saved-models/BasicLSTM_2024-04-27_21-46-28_trained_testAcc=0.7182.pth --loss_criterion bcelosswithlogits --only_test 1
