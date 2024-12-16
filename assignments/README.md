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
