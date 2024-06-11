# Hotel Recommendation System
This repository is about my semester project related to the course Big Data Analytics. I programmed a recommendation system based on Hotel Reviews Dataset.

A content-based recommendation system suggests new items that are similar to the ones a user previously rated highly. By examining attributes such as the hotel's facilities, location setting, and overall ambiance, the recommendation engine can pinpoint properties that closely match the tastes demonstrated by the user's positive review. This content-based approach analyzes the characteristics of the items themselves, rather than considering data about other users' preferences or behavioral patterns. As a result, it is well-suited for making personalized recommendations tailored to individuals with niche interests or highly specific requirements. This approach implements a content-based recommendation system for hotels based on their tags and average reviewer score. 

The dataset that I used for this project contains 515,000 customer reviews and scoring of 1493 luxury hotels across Europe. The dataset consisted of 17 columns however only 4 i.e. Hotel Name, Address, Tags and Average Reviewer were used in the implementation of the recommendation system. 

# Overview of the Steps employed in Implementation
First step in the process was to prepare the Tags column to extract important features of hotel.For this purpose, I created a function called removespaces to remove the space in each phrase of the tag for example the tag 'Solo Traveller' was changed to 'solotraveller'. Removing the spaces in the phrases allowed each tag to be represented as a single word so that TF-IDF Vectorization can be applied to extract the important features of hotels. TF-IDF assigns weights to each term (tag) based on its frequency in the document (hotel) and its rarity across all documents (hotels). Then I merged the resulting dataframe (top_tags) with the previous dataffame (hotel_df) and introduced a new column called Top_10_Tags. 

In the next step, I applied one-hot coding methodology to create a binary vector of each hotel where each element respresents the presence or absence of a specific tag. If a tag is present, its corresponding element is set to 1. Further, I calculated the similarity using the encoded tag vectors and average reviewer score using the cosine similarity formula.  Cosine similarity measures the cosine of the angle between two vectors and ranges from -1 to 1. A higher value indicates a greater similarity between the hotels. The result is an NxN matrix where N is the number of hotels and each row represents the similarity value for a hotel with all other hotels.

For the final step, I created a function named new_recommended_hotels which takes the hotel name as input along with cosine_similarity matrix and returns a list of top 10 most similar hotels to the given input. 

Overall, this content-based recommendation system offers a data-driven approach to suggesting hotels that are similar to the ones users have liked, enhancing the user experience in the hospitality domain.
