# Spotify Song Clustering Analysis

This project focuses on performing clustering analysis on the Spotify Million Dataset, which contains song names, artist names, links to the songs, and lyrics. The dataset can be utilized for song recommendations, song classification, and clustering songs based on their features.

## Dataset

The Spotify Million Dataset was obtained from Kaggle using the Kaggle API. The dataset is stored in a zip file named `spotify_millsongdata.csv.zip`. To extract the dataset, the following code was used:

```python
from zipfile import ZipFile

with ZipFile('data/spotify_millsongdata.csv.zip', mode='r') as zip_file:
    zip_file.extractall('data/')
```

## Text Preprocessing

Text preprocessing is a crucial step before applying the KMeans clustering algorithm. The provided code demonstrates a simple helper function, `preprocess_text()`, that converts the text into numerical features suitable for input to the KMeans algorithm. The preprocessing steps include:

- Removing stopwords and converting the text to lowercase.
- Applying stemming or lemmatization to reduce words to their root form.
- Employing the CountVectorizer module from the sklearn library to create a bag-of-words representation.
- Utilizing the TF-IDF (Term Frequency-Inverse Document Frequency) transformer to weigh the importance of words in the dataset.
- Applying dimensionality reduction techniques such as SparsePCA and scaling using StandardScaler.

## KMeans Clustering

After text preprocessing, the KMeans clustering algorithm is applied to the transformed data. The following evaluation techniques are employed:

- **Elbow Method**: Used to determine the optimal number of clusters by analyzing the inertia (within-cluster sum of squares) for different values of k.
- **Silhouette Analysis**: A graphical tool to measure how tightly grouped the samples within each cluster are. The silhouette score ranges from -1 to 1, where higher values indicate better-defined clusters.

## Word Cloud Analysis

To determine the most representative words in each cluster, word clouds are generated for each cluster sample. Word clouds provide visual representations of frequently occurring words, offering insights into the characteristics of each cluster.

## Conclusion

In this project, the KMeans clustering algorithm is applied to the Spotify Million Dataset for clustering analysis of songs. The text data is preprocessed to transform it into numerical features suitable for clustering. The optimal number of clusters is determined using the elbow method, and the tightness of the clusters is assessed using silhouette analysis. Finally, word clouds are generated to identify the most representative words in each cluster.

## Future Enhancements

Potential future enhancements for this project include:

- Exploring different clustering algorithms and comparing their performance.
- Incorporating additional features such as song metadata or audio features for more comprehensive clustering analysis.
- Developing a song recommendation system based on the clustering results.

By continuously refining the clustering algorithms and incorporating additional features, this project aims to improve song recommendations, genre classification, and provide valuable insights into the Spotify music dataset.
