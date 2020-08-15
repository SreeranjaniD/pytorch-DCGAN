# DCGAN implementation in PyTorch

I would like to sincerely thank the author of DCGAN tutorial for using their open-sourced source code in PyTorch. The code has been fully borrowed from the author's code. Example dataset has been added. 

The DCGAN code was written by Nathan Inkawhich (https://github.com/inkawhich)


Procedure:
 Clone the repository and save it in your Google Drive as pytorch-DCGAN. You can shift the python notebook to Colab Notebooks folder. Create  
 
### Data Preprocessing: 
Download preferred datasets using the following command in Google Collaboratory
!bash ./datasets/download_cyclegan_dataset.sh <dataset name>
  <dataset name>- horse2zebra, maps (for aerial photo to Google Maps), vangogh2photo
    
The images will be downloaded to the folder in Google Drive--> datasets--> <dataset name>
  
 You can also use the example dataset provided in the datasets folder.

## Training 
Create a folder by the name capstone_trained_model in pytorch-CycleGAN to save your experiment's results.


Command to mount Google Drive to Colab:
```
from google.colab import drive 
drive.mount('/content/gdrive')
```

Command to change the directory:
```
cd gdrive/My Drive/pytorch-CycleGAN
```

To train the model, 
```
!python train.py --dataroot ./datasets/<example dataset> --name <experiment name> --direction AtoB --checkpoints_dir capstone_trained_model --init_type kaiming --save_epoch_freq 10
```
To test the model, 
```
!python test.py --dataroot ./datasets/<example dataset> --model cycle_gan --name <experiment name> --direction AtoB --checkpoints_dir capstone_trained_model --num_test 2000  
```

# Experiment analysis 

Once you have trained the model, you can see the log loss file in the folder capstone_trained_model--> <experiment name> of your Google Drive. You can analyse the loss data and can even plot it to check for convergence. The test results are saved in pytorch-CycleGAN--> results folder
  
  
  ## Reference citation: 
```
DCGAN tutorial: https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html
```
```
DCGAN paper: Radford, Alec, Luke Metz, and Soumith Chintala. "Unsupervised representation learning with deep convolutional generative adversarial networks." arXiv preprint arXiv:1511.06434 (2015).
```
