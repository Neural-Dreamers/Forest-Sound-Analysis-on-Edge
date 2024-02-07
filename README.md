# Forest-Sound-Analysis-on-Edge

## Model Training

1.  Download the FSC22 data from https://www.kaggle.com/datasets/dakshinaranmal/fsc22-v1

     > Note : The dataset used in this study has one class removed due to ambiguity. To successfully run the notebooks it is necessary to get the updated version of FSC22 from the above mentioned url.

2.  Extract the download FSC22 - v1 dataset zip (archive.zip) in the dataset folder in the project file structure. Once extracted successfully there will be a subfolder named fsc22 inside the dataset folder.

3.  Create a Conda environment. (Python 3.10.12 was used during research)

4.  Activate the Conda environment.

5.  Install the following libraries in the Conda environment.

        conda install conda-forge::tensorflow
        conda install pytorch::pytorch
        conda install anaconda::numpy
        conda install anaconda::pandas
        conda install conda-forge::tqdm
        conda install conda-forge::librosa
    
        pip install soundfile==0.8.1
        pip install audiomentations
         
        conda install conda-forge::matplotlib
        conda install conda-forge::optuna

7.  Run the **AudioHandler** notebook.

    Once completed, the pickle file of FSC22 resampled at 20kHz will be inside the dataset -\> fsc22 -\> Pickle Files directory.

9.  Run the **Feature Generator** notebook providing necessary command line inputs as required.
   
    Once completed pickle files following given data augmentation and feature extraction techniques will be created inside the dataset -\> fsc22 -\> Pickle Files directory.

8.  Run notebooks of the selected models. (Ex: **AlexNet, DenseNet121, EfficientNetV2B0, InceptionV3, MobileNetV3-Small, ResNet50V2**)
  
    In every model notebook, first hyper parameters will be tuned, followed by model training and the model will be saved in the given directory.

       > Note : Provide a relative path inside the project directory to save the trained model.

## Model Compression

Models can be compressed mainly using two compression techniques namely Pruning and Quantization.

### Pruning

Pruning can be done following three approaches.

1.  Weight Pruning

      Run the **Weight Pruning** notebook providing necessary command line inputs as required.

2.  Filter Pruning

      Run the **Filter Pruning** notebook providing necessary command line inputs as required.

3.  Hybrid Pruning

      Run the Filter Pruning notebook for an already weight pruned model obtained using Weight Pruning notebook.

### Quantization

Quantization can be done following two approaches.

1.  Tensorflow model quantization

      Quantization of models of type .h5 can be quantized with this. Models which are initially trained or weight pruned can be quantized.
      
      Run the **TF_Quantization** notebook providing necessary command line inputs as required.

2.  OpenVINO model quantization

      Quantization of models of type IR (OpenVINO Intermediate Representation) can be quantized with this. Models which are filter pruned or hybrid pruned can be quantized.
      
      Run the **OpenVINO Quantization** notebook providing necessary command line inputs as required.

