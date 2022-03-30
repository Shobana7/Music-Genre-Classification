## Music-Genre-Classification

 OBJECTIVE 
 
​Classifying music according to the genre using machine learning technique has proved to be quite successful in extracting trends and patterns from large pool of data. This principle is applied in Music Analysis also.

ABOUT THE DATASET

GITZAN​ dataset is used. The dataset consists of 1000 audio tracks each 30 seconds long. It contains 10 genres namely, blues, classical, country, disco, hip-hop, jazz, reggae, rock, metal and pop. Each genre consists of 100 sound clips.

PREPROCESSING THE DATA

Before training the classification model the audio clips need to be converted from .au format to .wav format to make it compatible with python’s wave module for reading audio files. Open source Sox module is used for the conversion.

AUDIO LIBRARIES

​Main library used for audio acquisition

❖ Librosa

It is a Python module to analyze audio signals in general but geared more towards music. It includes the nuts and bolts to build a MIR(Music information retrieval) system. It has been very
well ​documented​ along with a lot of examples and tutorials.

FEATURE EXTRACTION

Every audio signal consists of many features. This step is to extract meaningful features from the audio files. To classify our audio clips, 5 features are chosen, i.e. Mel-Frequency Cepstral Coefficients, Spectral Centroid, Zero Crossing Rate, Chroma Frequencies, Spectral Roll-off. All the features are then appended into a .csv file so that classification algorithms can be used.

● Zero Crossing Rate

The ​zero crossing rate​ is the rate of sign-changes along a signal, i.e., the rate at which the signal changes from positive to negative or back. This feature has been used heavily in both ​speech recognition​ and ​music information retrieval​. It usually has higher values for highly percussive sounds like those in metal and rock.

● Spectral Centroid

It indicates where the ”centre of mass” for a sound is located and is calculated as the
weighted mean of the frequencies present in the sound. Consider two songs, one from a blues genre and the other belonging to metal. Now as compared to the blues genre song which is the same throughout its length, the metal song has more frequencies towards the
end. So spectral centroid for blues song will lie somewhere near the middle of its spectrum while that for a metal song would be towards its end.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/SpectralCentroid.png" height="400">

There is a rise in the spectral centroid towards the end.

● Spectral Rolloff
It is a measure of the shape of the signal. It represents the frequency below which a specified percentage of the total spectral energy, e.g. 85%, lies.


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/SpectralRolloff.png" height="400">

● Mel-Frequency Cepstral Coefficients
The Mel frequency cepstral coefficients (MFCCs) of a signal are a small set of features (usually about 10–20) which concisely describe the overall shape of a spectral envelope. It models the characteristics of the human voice.


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/MelFreq.png" height="400">

Here mfcc computed 20 MFCC s over 97 frames.

● Chroma Frequencies
Chroma features are an interesting and powerful representation for music audio in which the entire spectrum is projected onto 12 bins representing the 12 distinct semitones (or chroma) of the musical octave.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/ChromaFreq.png" height="400">
  
 CLASSIFICATION

After the feature is extracted​, we can use existing classification algorithms to classify the songs into different genres. We have used the following algorithms for classification:

● KNN

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/KNN.png" height="400">

● Random Forests

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/RandomForest.png" height="400">
  
● Neural Network

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/NeuralNetwork.png" height="400">

● SVM

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="/Images/svm.png" height="400">
 
 How to Run?
       
       music_genre_classification.py 
It can be run in the terminal using "python music_genre_classification.py " 
	
       Music_Genre_Classification.ipynb
Use jupyter notebook

