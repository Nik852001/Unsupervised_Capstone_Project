# Unsupervised_Capstone_Project

Project Summary -
* There were approximately 7787 records and 11 attributes in the dataset.

* We started by working on the missing values in the dataset and conducting exploratory data analysis (EDA).

* Using the following attributes to create a cluster: cast, country, genre, director, rating, and description The TFIDF vectorizer was used to tokenize, preprocess, and vectorize the values in these attributes.

* The problem of dimensionality was dealt with through the use of Principal Component Analysis (PCA).

* Using a variety of methods, including the elbow method, silhouette score, dendrogram, and others, we constructed two distinct types of clusters with the K-Means Clustering and Agglomerative Hierarchical clustering algorithms, respectively, and determined the optimal number of clusters.

* The similarity matrix generated by applying cosine similarity was used to construct a content-based recommender system. The user will receive ten recommendations from this recommender system based on the type of show they watched.


Data Description :
* **show_id:** Unique ID for every Movie/Show
* **type:** Identifier - Movie/Show
* **Title :** Title of the Movie/Show
* **director:** Director of the Movie/Show
* **cast:** Actors involved in the Movie/Show
* **country:** Country where the Movie/Show was produced
* **date_added:** Date it was added on Netflix
* **release_year:** Actual Release year of the Movie/Show
* **rating:** TV Rating of the Movie/Show
* **duration:** Total Duration - in minutes or number of seasons
* **listed_in :** Genre
* **description :** The Summary description

Problem Statement:
Netflix is a streaming service that offers a wide variety of television shows and movies for viewers to watch at their convenience. With a monthly subscription, users have access to a vast library of content, including original series and films produced by Netflix. The platform also allows users to create multiple profiles, making it easy for family members or roommates to have their own personalized viewing experience. Additionally, Netflix allows users to download content to watch offline, making it a great option for those who travel frequently or have limited internet access. Overall, Netflix is a convenient and cost-effective way to access a wide variety of entertainment.

As of 2022-Q2, more than 220 million people had signed up for Netflix's online streaming service, making it the largest OTT provider worldwide. To improve the user experience and prevent subscriber churn, they must efficiently cluster the shows hosted on their platform.

By creating clusters, we will be able to comprehend the shows that are alike and different from one another. These clusters can be used to provide customers with individualized show recommendations based on their preferences.

This project aims to classify and group Netflix shows into specific clusters in such a way that shows in the same cluster are similar to one another and shows in different clusters are different.

Business Context:
Clustering Netflix movies and TV shows is crucial for enhancing user experience and optimizing business operations. It allows Netflix to improve content recommendations, streamline content acquisition and creation, fine-tune marketing strategies, and tailor offerings for specific user segments. By leveraging clustering analysis, Netflix can stay competitive, ensure content quality, and drive user engagement, ultimately leading to increased subscriber satisfaction and retention.


Exploratory data analysis:

1. Column:'type'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/9f12da7e-4298-43e9-ac21-02582f52adcc)
**Observations:**

* Movies have more number of counts than TV Shows.
* 31% of the data are from TV shows, while 69% of the data are from movies.

2. Column:'title'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/8508ac11-d872-4ef2-8b32-9cdc4e893853)
**Observations:**

* The three shows directed by Alastair Fothergill are the highest on the data list.
* Both, Jan Suter and Raul Campos have directed 18 films, more than anyone else in the dataset.

3. Column:'cast'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/fe1e9e67-49d2-4052-9df0-8bb1edc794c4)
**Observations:**

* The majority of the roles in the movies are played by Anupam Kher, Shahrukh Khan, and Om Puri.
* In the shows, Takahiro Sakurai, Yuki Kaji, and Daisuke Ono played the most number of roles.

4. Column:'director'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/32dd311b-9a01-4657-82a8-6b365d1d7199)
**Observations:**

* The three shows directed by Alastair Fothergill are the highest on the data list.
* Both, Jan Suter and Raul Campos have directed 18 films, more than anyone else in the dataset.

5. Column:'country'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/8e8513e2-9995-4d44-80bc-5bec3ef77065)
**Observation:**
* The United States-based movies and TV shows were produced most, followed by India and the United Kingdom.
* In India and the United States, a greater number of movies are present compared to TV shows.
* In the UK, Japan, and South Korea there are a greater number of TV shows than movies.

6. Column:'release_year'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/9a56dbef-9c50-4025-befe-ff3720ca1070)
**Observations:**

* Netflix has started releasing more Movies/TV shows in recent years compared to old ones.
* Most Movies and TV shows were available on Netflix between 2015 and 2020, and the highest were in 2018.

7. Column:'rating'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/5ec8d918-a978-412d-b7d0-7a2b46721fde)
**Observations:**

* The majority of Movies and TV shows have a rating of TV-MA, which stands for "Mature Audience," followed by TV-14, which stands for "Younger Audience."
* When compared to TV shows, Movies receive the highest rating, which is pretty obvious given that the number of Movies is higher compared to TV shows, as we saw earlier in the type column.

8. Column:'listed_in'
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/64a1d1ff-5edf-4e8d-8a08-f733d11c78d6)
**Observations:**

* International Movies, Dramas, and Comedies make up the majority of the genres.
* TV Shows, Classic and cult TV, TV thrillers, Stand-Up comedy, and Talk shows account for the least genres.


Model Implementation:
1. K-Means Clustering:
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/535d0484-d251-4bbd-887d-28fc392665d0)

![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/d3b63b8e-6b9c-4b31-9d50-ad5a1a147c31)

![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/195e5dc6-f54c-4ade-b921-2fa1c091019b)

3. Hierarchical Clustering:
   
![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/df26c554-5f89-4966-aeb1-7df7ca349f46)

![image](https://github.com/Nik852001/Unsupervised_Capstone_Project/assets/93510310/c7d0e20d-496f-4968-97b7-4a094e3934cc)



Conclusion:
In this project, we tackled a text clustering problem in which we had to categorize and group Netflix shows into specific clusters in such a way that shows in the same cluster are similar to one another and shows in different clusters are not.

* There were approximately 7787 records and 11 attributes in the dataset.
* We started by working on the missing values in the dataset and conducting exploratory data analysis (EDA).
* It was discovered that Netflix hosts more movies than television shows on its platform, and the total number of shows added to Netflix is expanding at an exponential rate. Additionally, most of the shows were made in the United States.
* The attributes were chosen as the basis for the **clustering of the data: cast, country, genre, director, rating, and description** The TFIDF vectorizer was used to tokenize, preprocess, and vectorize the values in these attributes.
* **10000 attributes** in total were created by **TFIDF vectorization**.
The problem of dimensionality was dealt with through the **use of Principal Component Analysis (PCA). Because 3000 components were able to account for more than 80% of the variance**, the total number of components was limited to 3000.
* Utilizing the **K-Means Clustering algorithm**, we first constructed clusters, and the **optimal number of clusters was determined to be 6**. The **elbow method and Silhouette score analysis** were used to get this.
* The **Agglomerative clustering algorithm** was then used to create clusters, and the **optimal number of clusters was determined to be 7**. This was obtained after visualizing the **dendrogram**.
* The similarity matrix generated by applying **cosine similarity** was used to construct a **content-based recommender system**. The user will receive ten recommendations from this recommender system based on the type of show they watched.










