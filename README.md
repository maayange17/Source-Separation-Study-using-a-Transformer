# Source-Separation-Study-using-a-Transformer
An initial attempt to discover instrument sounds with a transformer. Developed based on Meta's architecture and research.
## Original code:
### 1. Spacetimeformer - https://github.com/QData/spacetimeformer
### 2. Hdemucs - https://github.com/facebookresearch/demucs <br/>
Try to follow to installation of libraries in each project before you start with our code!
To understand how to run basic Hdemucs, you need to read first: https://github.com/facebookresearch/demucs/blob/main/docs/training.md <br/>
After the basic installations and understand of running the demucs, you may strat!

## Changes in code + debug
### 1. Copysongfiles
With the full dataset, debugging the architecture can take time after minor or major changes. For debugging purposes, you can simply create a smaller dataset. Update the path where the MUSDB18HQ dataset exists and the path where the reduced dataset should be located.
### 2. Train_a_smaller_architecture
Helps us to make Meta's architecture smaller and train it. In addition, we added a log of training and testing for the original (but smaller) architecture. The last log contains the results that we present in our paper.
### 3. Train_T
In this notebook, we show the results of Meta's architecture + Spacetimeformer, in order to select hyperparameters for the Spacetimeformer in this project. This notebook is not for running code.
### 4. Facebook_Transformers
This is a folder with Meta's code and the changes that we did to link Meta's original architecture to the Spacetimeformer. We made many changes in the code, most of them are visible at: 'Facebook_Transformers/demucs-main/demucs-main/demucs'. There, you can see our new layer, and how it connects to orignal architecture and how we replace the LSTM + local attention with Spacetimeformer.
### 5. spacetimeformer-main
Here, we have both the original zip file of Spacetimeformer project and the file after the changes we did. **The original code will not work, use the folder!**
We made changes to the inputs of the model,as well as changing embed file (both in 'nn' files of the Spacetimeformer).
### 6. Model_with_transformer_full_run_logs
Here, you will see the full logs of the running of our model. The last log is the log with the results that we show in our paper.
Also show commands of how to run the model.

### Important details: 
a. Remember to update the main_path <br/>
b. Remember to update the paths of the dataset and everything else in: Facebooks_code_for_tensors folder and Facebook_Transformers folder if you wish to train the model, using Meta's training doc: https://github.com/facebookresearch/demucs/blob/main/docs/training.md <br/>
c. We used dora, a great tool to change and follow the changes of the hyperparameters. Read about it more in Meta's training doc. <br/>
d. We started from 81de367c in the training, as this the original Hdemucs. 

### Not so important details:
Facebook's_code_for_tensors is a copy of Meta's code we used for debugging. We saw a lot of changes in the data in Facebook_code_for_tensors/demucs-main/demucs-main/demucs/wav.py on 'get_item', so we saved the final product and loaded it as tensor in the next training. Ultimately, we didn't use it since the I/O time of h5 is the same as the time of changes in data.


