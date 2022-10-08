# Source-Separation-Study-using-a-Transformer
Initial research to discover the instrument sounds of a song with a transformer. Based on Meta architecture and research.
## Original code:
### 1. Spacetimeformer - https://github.com/QData/spacetimeformer
### 2. Hdemucs - https://github.com/facebookresearch/demucs
## Changes in code + debug
### 1. Copysongfiles
Runs to debug the architecture after small changes or big changes, may take time with the full dataset. Therefore, for debugging purposes, you can create a smaller dataset with the click of a button. It is important to update the path where the MUSDB18HQ dataset exists and the path where we want the reduced dataset.
### 2. Train_a_smaller_architecture
Helps use to take the architecture of Meta, make is smaller, and train it. Moreover, we added the log of training and testing for the original (but smaller) architecture. The last log is the log with the results that we show in our paper.
### 3. Train_T
This is a notebook that shows small the results of the Meta's architecture + Spacetimeformer, the point of this notebook is to show the initial runs we did in order to choose hyperparameters of the Spacetimeformer in this project. This note book is not to running code.
### 4. Facebook_Transformers
This is a folder with Meta's code and the changes that we did to link between Meta's original architecture to the Spacetimeformer. We did many changes in the code, most of them are visible at: 'Facebook_Transformers/demucs-main/demucs-main/demucs'. There, you can see our new layer, and how it connects to orignal architecture and how we replace the LSTM + local attention with Spacetimeformer.
### 5. spacetimeformer-main
Here, we have both the original zip file and the file after changes we did. **The original code will not work, use the folder!**
We did changes to the inputs of the model and to the embed files (both in 'nn' files of the Spacetimeformer) to match our inputs and outputs of the model.
### 6. Model_with_transformer_full_run_logs
Here, you will see the full logs of the running of our model. The last log is the log with the results that we show in our paper.
Also show commands of how to run the model.

### Important details: 
a. Remember to update the main_path <br/>
b. Remember to update the paths of the dataset and everything else in: Facebooks_code_for_tensors folder and Facebook_Transformers folder if you wish to train the model, using Meta's training doc: https://github.com/facebookresearch/demucs/blob/main/docs/training.md <br/>
c. We used dora, a great tool to change and follow the changes of the hyperparameters. Read about it more in Meta's training doc. <br/>
d. We started from 81de367c in the training, as this the original Hdemucs. 

### Not so important details:
The folder Facebooks_code_for_tensors is a copy of Meta's code we used for debugging purposes. The name is from the fact that we saw in 'Facebooks_code_for_tensors/demucs-main/demucs-main/demucs/wav.py' in 'get_item' a lot of changes in the data, and we tried to save the final product and load it ad tensor in the next training, to save up some time. But it looks like the changes in data and the I/O time of h5 are the same, so we didn't use it in the end.

