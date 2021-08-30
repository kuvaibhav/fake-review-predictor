# Fake-Review-Predictor (Restaurants and Hotel Customer Reviews)
Online reviews play an important role in making informed decisions on the purchase of a product/service.
Statistics show that 74% of all users use online reviews to build trust. Furthermore, we see a 390% increase in
sales of products with a review rating of 4 or more while 86% of consumers hesitate to buy a product with
negative reviews. The increasing popularity of online reviews also stimulates the business of fake review
writing, which refers to paid human writers producing deceptive reviews to influence readers' opinions. Nike, for
example, in 2019 decided to stop selling their products on Amazon as they felt it undermined their products.
Moreover, with critical industries like healthcare moving to online platforms, their ability to maintain credibility is
being questioned more than ever. This project tackles this problem by building a BERT based classifier that takes the review
text and the information of its reviewer as input and outputs whether the review is reliable.

#Dataset
All the data has been collected from Yelp.com by Rayana and Akoglu and it includes product and user
information in the form of an ‘ID’, timestamp, ratings and plaintext review.

#Data Cleaning and Feature Extraction
For the text reviews, we removed punctuations, special characters and stop words from our dataset. Although
the dataset had a lot of metadata like user id, product id, review date etc, only the text
reviews, the ratings, and the fake review indicator were chosen as other metadata didn't provided any further improvemnt on BERT model. 
LDA model of text reviews were performed to visualise the various topics included in text
reviews. Making this visualization confirmed that dataset is indeed a restaurants and hotel review dataset,
since most of the topics revolve around food and customer service.
![image](https://user-images.githubusercontent.com/41999054/131270234-f9116dd1-58e0-4690-93e1-c4284668974f.png)

End Result: 
For initial analysis the review centric features were not considered and the model was trained only on text and
corresponding labels. Training was done on GPU provided by Google Colab.For the next part, additional
features were extracted from the dataset and appended to the original review text. This gave higher accuracy.

An accuracy of around 78% on BERT was seen for fake review detection when input to the model was only
review texts. When review centric features were added to the model, a sharp increase in accuracy
(~95%) was observed. This leads to conclude that for fake review detection, additional information such as user related
information, time and source of review and other review centric features play an important role. This also
explains that Yelp’s spam filter works not just based on the reviews, but also based on the metadata.

![image](https://user-images.githubusercontent.com/41999054/131270335-0217979d-45ab-4150-a814-53145fbb9914.png)

![image](https://user-images.githubusercontent.com/41999054/131270347-204a0a41-fa70-4629-b60a-d6c7ab26b436.png)

