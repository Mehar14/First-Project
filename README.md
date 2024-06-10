# First-Project
This is my first public repository about my semester project related to the course Big Data Analytics. I developed a recommendation system model based on Hotel Reviews Dataset. Read more about the implementation in markdown file.

Content Based Recommendation System
A content-based recommendation system suggests new items that are like ones a user previously rated highly. By examining attributes such as the hotel's facilities, location setting, and overall ambiance, the recommendation engine can pinpoint properties that closely match the tastes demonstrated by the user's positive review. This content-based approach analyzes the characteristics of the items themselves, rather than considering data about other users' preferences or behavioral patterns. As a result, it is well-suited for making personalized recommendations tailored to individuals with niche interests or highly specific requirements. This approach implements a content-based recommendation system for hotels based on their tags and average reviewer score. 

About the Dataset
This dataset contains 515,000 customer reviews and scoring of 1493 luxury hotels across Europe. Hotel Name, Address, Tags and Average Reviwer score for each hotel were selected as important tags to implement the recommendation system model. 
 
Preprocessing the Tags Feature:
The removespaces function is applied to clean and format the tags column, ensuring consistency and removing unnecessary spaces or characters.
 
TF-IDF Vectorization:
TF-IDF (Term Frequency-Inverse Document Frequency) vectorization is applied to extract the top 10 most important tags for each hotel. TF-IDF assigns weights to each term (tag) based on its frequency in the document (hotel) and its rarity across all documents (hotels).
 
One-Hot Encoding:
The important tags extracted using TF-IDF are encoded using one-hot encoding. For each hotel, a binary vector is created where each element represents the presence or absence of a specific tag. If a tag is present, its corresponding element is set to 1.
 
Calculating Similarity:
Cosine similarity is calculated between hotels based on their encoded tag vectors and average reviewer score. Cosine similarity measures the cosine of the angle between two vectors and ranges from -1 to 1. A higher value indicates a greater similarity between the vectors. The output shows the sorted similarity data frame based on the similarity value between hotels.
 
Recommendation Generation:
When a user inputs a hotel name they liked, the system retrieves the encoded tag vector and average score for that hotel. The output is a sample to test the recommendation system. Input hotel name The Wittmore Adults Only is given and recommended hotels are presented.
 
Overall, this content-based recommendation system offers a data-driven approach to suggesting hotels that are similar to the ones users have liked, enhancing the user experience in the hospitality domain.

