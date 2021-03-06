# Bayes_Naive_Model_text_classification


Following is the statement of the problem: “Given a document, can we classify it in its appropriate category”?”    

The approach to solve the problem is simple. We have a finite set of topic that are the hidden variables acting on the words that are the observables. We can draw a simple Bayesian network to represent the interactions between the topics and the words. 

<img src="https://github.com/allarassemjonathan/Bayes_Naive_classifier/blob/main/PictureBayesian.png">

Where Ck is a random variable representing the topics, xi a random variable representing a word in the sequence of words. 
The task will be to maximize the value of y using the following equation:

<img src="https://github.com/allarassemjonathan/Bayes_Naive_classifier/blob/main/Equation(1).PNG">

where y is the topic that maximizes the posterior probability, Ck is the set contatining the topics and x is the set of observables.

We learn the posteriors probabilities distribution by counting the number of words occurring in each document after removing the stop words. We end up with a probability distribution for each of our topic, a sort of table that map the probabilities of word occurring with the condition of it being used in that topic. 
After iterating through more than 20 articles we have the following distribution of words depending on the topic:
For politics,

<img src="https://github.com/allarassemjonathan/Bayes_Naive_classifier/blob/main/PicturePolitics.png">

For sports,

<img src="https://github.com/allarassemjonathan/Bayes_Naive_classifier/blob/main/PictureSport.png" >

For science,

<img src="https://github.com/allarassemjonathan/Bayes_Naive_classifier/blob/main/PictureScience.png" >

The algorithm derives p(x|Ck) based on a multinomial distribution . We generate a Conditional Probability Table for each of the topic that we use for that computation. These tables are generated by learning structure from the data. We used about 20 articles for each topic coming from diverse sources like Fox news, CNN, Washington Posts ect... and the program learned the different posterior probabilities from these articles. 

We were able to achieve a solid 98% accuracy on the included test data. 
