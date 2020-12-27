# Tweets_2020_US_Election

Social media has become an emerging platform for expressing opinion, while still posing many challenges involving structure, quantifiability and representability. Twitter contains tweets with associated hashtags and geotags, providing new opportunities to unveil geographic locations of users expressing their opinions. In this research, I use Twitter’s unique usage of hashtags in training a similarity network model to reveal voter intentions expressed in tweets related to the 2020 United States Presidential Election. A similar study was carried out by my mentor, Dr. Thill and his colleague, Dr. Gong with regard to the 2016 United States Presidential Election: Gong Z, Cai T, Thill J-C, Hale S, Graham M (2020) Measuring relative opinion from location-based social media: A case study of the 2016 U.S. presidential election. PLoS ONE 15(5): e0233660.https://doi.org/10.1371/journal.pone.0233660

This research proposes a novel approach to measure the voting intentions of Twitter users in the 2020 Presidential Election. By pulling any and all tweets containing keywords ‘Trump’ or ‘Biden’, while limiting tweets to those that contain English language and geolocation, we ensure candidate sentiment can be reasonably discerned and eventually mapped to a United States user’s state of origin. My role in the research involved creating robust training data with hashtagged tweets by building a similarity network to properly categorize the hashtags into Pro and Anti candidate labels. These opinion categories can then be used as input for a new deep learning method devised by Dr. Gong called Opinion-Oriented Word Embedding. Because word embedding allows for vector representations rather than categorical ones, we end up with a more nuanced, full spectrum of user sentiment regarding the candidates. The idea is that once trained, the model will be able to predict candidate preference from tweets whether or not hashtags are used. 

Our preliminary findings from network analysis suggest that although Donald Trump has a much stronger support base than Joe Biden, there is overwhelming negative sentiment towards the President in part due to the pandemic and Black Lives Matter movement, whereas Joe Biden enjoys minimal unfavorability. Of note is the significance of noise involved due to the pandemic and 4-month lag in capturing sentiment further away from election time.

An overview of the objectives involved:
<ol>
  <li>Collection of desired Twitter data</li>
•Output: compressed, raw tweet JSON files from March to June 2020
  <li>Data preparation</li> 
•Input: compressed, raw tweet JSON files from step 1
•Output: 1 CSV table containing only hashtagged tweets, 1 CSV file containing tweets without hashtags
•Tweets contain TRUMP or BIDEN keyword in the tweet record. Each tweet originates from an official Twitter client and U.S. geolocation 
  <li>Generation of training setfrom hashtags</li>
•Input: 1 CSV table containing only hashtagged tweets from step 2
•Output: training files – two text files for candidates and one vocab CSV file 
  <li>Extraction of geolocation of users and assignment of users to states</li> 
•Input: 1 CSV table containing tweets without hashtags from step 2
•Output: 1 CSV table along with state designations of unique users
  <li>Opinion-Oriented Word Embedding training</li>
•Input: training files from step 3
•Output: word embedding file
  <li>Embedding aggregation and opinion plot and prediction</li>
•Input: embedding file from step 5 and CSV table from step 4
•Output: opinion plots and prediction results
