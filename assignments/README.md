# Verba

In this final project, we’ll use **Wav2Vec2.0** to get transcripts of audio files. Instead of building a model from scratch and training it on a large dataset, which takes a lot of time and resources, Wav2Vec2.0 offers a quicker and easier solution. It’s already trained on a huge amount of audio data, so we can use it right away for accurate results without needing to worry about the complicated details.

- ### Transformers

    Transformers are deep learning models designed for processing sequential data, such as text, audio, or time-series, using a mechanism called **self-attention**. Unlike traditional RNNs, transformers process entire sequences in parallel, making them highly efficient and scalable. The architecture consists of an **encoder-decoder structure** where the encoder focuses on understanding input relationships, and the decoder generates the output.

    To dive deep into transformers, check out this [YouTube playlist](https://www.youtube.com/playlist?list=PLKnIA16_RmvYuZauWaPlRTC54KxSNLtNn). Focus on videos 68 to 73 (skip 70) for detailed explanation.


- ### Wav2Vec 2.0

    Wav2Vec2.0 is a transformer-based model designed for speech-to-text tasks. It processes raw audio waveforms directly, eliminating the need for manual feature extraction like MFCCs. The model is pre-trained on unlabeled audio using a contrastive learning objective to learn speech representations, then fine-tuned on labeled audio-text pairs for transcription.

    For a detailed understanding of the architecture of Wav2Vec2.0, refer to this article: **[An Illustrated Tour of Wav2vec 2.0](https://jonathanbgn.com/2021/09/30/illustrated-wav2vec-2.html)**


Here is a brief overview of what exactly you are required to do:

1. Import the necessary libraries. Use `transformers` library to import `TFWav2Vec2ForCTC` and `Wav2Vec2Tokenizer` classes.

2. Make instances of the **Wav2Vec** model and **Wav2Vec2Tokenizer** tokenizer.

3. Audio Preprocessing: 
    - Load the audio files.
    - Resample them to a sample rate of 16000 (this specific sr is required by Wav2Vec model).
    - Normalize the audio.
        > There are some reasons we are normalizing the audio file:  
        > - Wav2Vec2.0 is trained on audio data that is normalized. Feeding unnormalized audio may lead to poor results.
        > - Raw audios can have amplitudes exceeding the maximum allowable range. This could lead to distortion during processing.
4. Tokenize the audios.
5. Make predictions.
6. Decode predictions to get the transcripts.

> There is no need to fine tune the model. After following these steps, you should get nice results.


## Assignment - 01
### Sentiment Analysis

The aim of this assignment is to implement concepts learnt during second week in python. You need to implement a model to classify text sentiment using tensorflow. The dataset used is `IMDB Dataset of 50K Movie Reviews`. You can download the dataset from here [here](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews). You need to submit this assignment by 22 December, 2024.  

Here are some points that might help you:

1. If you are using google colab for doing this assignment (which you are advised to do), you can use the following steps to directly download the dataset from kaggle:
    - Download the dataset:  
        ```bash
        !kaggle datasets download -d lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
    - Extract it:
        ```python
        import zipfile
        zip_ref = zipfile.ZipFile('/content/imdb-dataset-of-50k-movie-reviews.zip', 'r')
        zip_ref.extractall('/content')
        zip_ref.close()

2. The basic outline of what you have to is as follows:
    - Download the dataset.
    - Preprocess the data.
    - Tokenize the movie reviews.
    - Make and train the model that gives best results.


## Assignment - 02
### Mini Speech Recognition

The aim of this assignment is to comvert short spoken commands to text. The dataset you need to use can be downloaded from [here](http://storage.googleapis.com/download.tensorflow.org/data/mini_speech_commands.zip).  

1. To download the dataset directly in the google colab, you can use `wget` library. Run the following command to install it in google colab:  

        ```python
        !pip install wget

2. Consider using `glob` library for loading the dataset. Run the following command to install it in google colab:

```python
!pip install glob