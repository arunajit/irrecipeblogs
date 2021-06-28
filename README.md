## Information Retrieval Package on Recipe Blogs
Information Retrieval on Recipe Blogs
<br>
# Intention:<br>
With the easy availability of the internet and the latest interest of people to prepare 
their favourite food, Food Blogs have become a thing of relevance today. From searching for 
one pot meals to innovative 5 star entrees, from easy snacks to the very traditional regional 
dishes, people have started to search for recipes specifically, or with certain conditions or by 
the ingredients that are readily available. Thus retrieval of the most relevant recipes by 
ingredients and the rating and cooking time gets prominence.
<br>
# Phase 1 & 2 <br>
After the extracting, cleaning, filtering and transformation phases the data is ready for 
further procedures. Here for ranking and querying we have used three different approaches.<br>
1) Cosine Similarity
Plain old cosine similarity approach to find the matching strings (title) and 
output the top – 10.<br>
2) Enumerated Index based String matching
Enumerated string lists is taken and index-based string matching is done to 
display the results<br>
3) Fuzzy String Matching
Using fuzzywuzzy library the matching is done via approximation, 
Levenshtein distance the basic metric used here, calculated in ratios between 
two strings the matching is done – Used four different approaches here,
  a) W Ratio
  b) Partial Ratio
  c) Token Sort Ratio
  d) Token Set ratio
<br>
# Phase 3 <br>

In phase 3, using the preprocessed data, clustering and recommendation of similar recipes has
been done. The recommendations have been evaluated through some metrics.
The clustering technique was inspired from the paper ‘Hierarchical Clustering for Collaborative
Filtering Recommender Systems’ Chalco.et.al<br>

For the Agglomerative Clustering of the data, the data was vectorised and Agglomerative
clustering was done with the number of clusters ranging between 2 and 10.<br>

The optimal number of clusters were found to be ‘7’ through the average silhouette score of the
cluster. As shown above, it is only when the number of clusters is 7 does the silhouette score
reaches the peak. The dendogarm for the data was also done to counter-check the optimal
number of clusters.<br>

Thus the optimal number of clusters were fixed as 7 and further works for recommendations
were done.<br>
Now, when the user queries for a particular recipe, the particular recipe were search and
retrieved. But along with it a set of recommended dishes similar to the one queried were also
retrieved.<br>

The retrieved and recommended dishes were evaluated using the ‘precision at k’ metric, where
‘k’ is the number of recommendations done to the user. The dish belonging to the same cuisine
as the most relevant recipe to the queried recipe was considered to be relevant and the
precision at k was computed for the given query.<br>

Due to the unavailability of the information on whether the recipe was relevant or not, the above
method of relevance marking was done. Due to this factor, other metrics like recall were not
computed.<br>
