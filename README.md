# NeuralNetworksProject-Music-Source-Separation

Instructions to run the project

I replicated the Hybrid Transformer Demucs for Music Separation project on a GoogleColab file.
In order to run all the function I have implemented and listen to the output files you need to execute the notebook.


# Separate any song you have on GoogleDrive

I decided to use my Google Drive to load the input and to store the outputs. 
So I create two folders: the first called “demucs’”and the second called “demucs_separated”. 

In order to execute the separation of a song in the 4 sources (drums,bass,vocals and other) you have to choose a song that you like, which can be in the .mp3 or .wav format, and load it into a “demucs“ named folder on your GDrive .

After you have ran the separation function you will find in the “demucs_separated” folder the 4 different files that will reproduce the instruments of the song. It will also generate a folder for each model you will choose.

NB: You can also load multiple songs per time, it will only takes longer.

Otherwise, to try my personal separate function it will store remotely the audio files and you can listen to them directly on Colab.

# Train the model

In order to train the model, unfortunately you have to do it locally. 
Firstly you have to install all the dependencies using:

```
conda env update -f environment-cpu.yml  (if you don't have GPUs)
conda env update -f environment-cuda.yml  (if you have GPUs)
conda activate demucs
pip install -e 
```


This will create a demucs environment with all the dependencies installed.

Then you have to install MUSDB-18HQ dataset at this link: https://zenodo.org/record/3338373#.Y-fNvuzMK3I

At this point you have to update with your setup the “dset.musdb “ key inside ```conf/config.yaml``` and the variable “MUSDB_PATH” inside ```tools/automix.py```. 

NB: ```config.yaml``` and ```tools/automix.py``` are in the repository of demucs which was installed before with the environment creation.

Then you have to use Dora (more info on the Colab File) in order to train the model.
The github repo is here: https://github.com/facebookresearch/dora .

For evaluation you can follow the Colab File instructions but also in this case it is only locally.


# Details and plots are reported in the Colab notebook

