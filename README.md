# Akeed_Restaurant_Recommendation_Challenge

Repo to collaborate on the Akeed restaurant recommendation challenge.

## Objective

The objective of this competition is to build a recommendation engine to predict what restaurants customers are most likely to order from given the customer location, restaurant information, and the customer order history.

This solution will allow Akeed, an app-based food delivery service in Oman, to customise restaurant recommendations for each of their customers and ensure a more positive overall user experience.

## Data

There are ~10,000 customers in the test set. These are the customers you will need to recommend a vendor to. Each customer can order from multiple locations (LOC_NUM).

There are ~35,000 customers in the train set. Some of these customers have made orders at at least one of 100 vendors.

The objective of this competition is to build a recommendation engine to predict what restaurants customers are most likely to order from, given the customer location, the restaurant, and the customer order history.

* test_customers.csv - customer id’s in the test set.
* test_locations.csv - latitude and longitude for the different locations of each customer.
* train_locations.csv - customer id’s in the test set.
* train_customers.csv - latitude and longitude for the different locations of each customer.
* orders.csv - orders that the customers train_customers.csv from made.
* vendors.csv - vendors that customers can order from.
* VariableDefinitions.txt - Variable definitions for the datasets
* SampleSubmission.csv - is an example of what your submission file should look like. The order of the rows does not matter, but the names of CID X LOC_NUM X VENDOR must be correct. The column "target" is your prediction. The submission file is large so please allow up to 30 minutes for your score to reflect.

## Evaluation

The error metric for this competition is the F1 score, which ranges from 0 (total failure) to 1 (perfect score). Hence, the closer your score is to 1, the better your model.

F1 Score: A performance score that combines both precision and recall. It is a harmonic mean of these two variables. The formula is given as: 2*Precision*Recall/(Precision + Recall)

Precision: This is an indicator of the number of items correctly identified as positive out of total items identified as positive. The formula is given as: TP/(TP+FP)

Recall / Sensitivity / True Positive Rate (TPR): This is an indicator of the number of items correctly identified as positive out of total actual positives. The formula is given as: TP/(TP+FN)

Where:

* TP=True Positive
* FP=False Positive
* TN=True Negative
* FN=False Negative

Your submission file should look like:

Where 1 indicates that a customer will order from that restaurant and 0 that they will not order from that restaurant.

|CID X LOC_NUM X VENDOR |    target                    |
|-----------------------|:-----------------------------|
|A7B8IGM X 0 X 105      |      0
|NS70FA9 X 0 X 105      |      1
|WTWOE69 X 0 X 105      |      0

## Helpful hints in the discussion board

For preparing test data, the hint is in sample submission. Drop duplicates for test customers. Merge test customer and location and then, for each row of test add all rows of vendors. Then create the id column using the three columns mentioned in the name of sample submission id. Try to make the number of rows in the test similar to sample submission.Follow the same steps for the train. This should get you started.

Q) And what about "orders"?

A) "Orders"- Use it to make target. If ID of train is present in orders then target is 1..if not then 0

Q) Hi, I don't see why duplicate customers have to be ruled out ... the fact that it is duplicate is because the same customer is in another restaurant. If we eliminate the duplicates then we are going to predict the probability only in a restaurant. Another thing that is not clear to me in your methodology is the assessment ("vendor_rating") ... finally, collaborative filters, for example, make use of these metrics to obtain similarity matrices. PS: In fact, I'm not quite sure if it is necessary to get a binary variable (0 and 1) as target ... Regards.

A) look at the data before writing. test customer CSV has nothing to do with restaurants. it is all information about customer. And when you finally spend some time with data you will realise the same customer has a verified and and unverified detail which should be removed. As you won't get same number of rows as sample submission. But again for this you have to spend time with the data before commenting.

Q) Some of the customerID's (CID) in the Sample Submission file are not present in the test_customer file.

A) Hi Suraj, Yes. But full test customer detail is obtained when you merge test customer and test location, after removing duplicates as I have mentioned. After merging if you find set intersection of merged ID and submission file, you will get all IDs of the sample in the test.

Q) Just started looking at the data of this competition - nice real-world type of data. But the location information is totally non-sensicle. I know that the coordinates have somehow been obscured to protect the customers, but if you look at the spread of lat and long it's all over the place, and even the locations _very_ far away from any vendors have valid orders, which does not make sense either.

A) The locations have been obscured, in a fairly reasonable way. However, the data as it arrived from the real world had all sorts of complications - sometimes latitude and longitude were the same value, sometimes they were both 0 (which got mapped by the processing to a weird coordinate)... If this happened on a job you'd likely ask for a meeting with the app/database folks to have a chat about how mangled the locations are! As it is this is all we've got :)

As Flitx mentioned, you could try to use other features. But we included this in case it's possible to get something useful. I'd suggest maybe clustering and excluding the glitchy values somehow, or doing as you've done and just looking at a vendor_distance feature but again excluding anything unreasonable. Might still have some predictive power.

Q) In the description of the challenge, "the objective ... is to build a recommendation engine to predict what restaurants customers are most likely to order from given ... the customer order history." However, we are given no indication of the order history of customers in the test set. In fact, there are zero customers in common between the training set and the test set. How have you worked around this?

A) The workaround is to treat this like a cold-visitor recommendation. Try to cluster customers based on features they have in common, then recommend the most popular restaurants in train for the customers in test in the same cluster.Another way is to treat it strictly as a classification problem.


## Rules

Teams and collaboration

You may participate in this competition as an individual or in a team of up to four people. When creating a team, the team must have a total submission count less than or equal to the maximum allowable submissions as of the formation date. A team will be allowed the maximum number of submissions for the competition, minus the highest number of submissions among team members at team formation. Prizes are transferred only to the individual players or to the team leader.

Multiple accounts per user are not permitted, and neither is collaboration or membership across multiple teams. Individuals and their submissions originating from multiple accounts will be disqualified.

Code must not be shared privately outside of a team. Any code that is shared, must be made available to all competition participants through the platform. (i.e. on the discussion boards).

Datasets and packages

The solution must use publicly-available, open-source packages only. Your models should not use any of the metadata provided.

You may use only the datasets provided for this competition.

The data used in this competition is the sole property of Zindi and the competition host. You may not transmit, duplicate, publish, redistribute or otherwise provide or make available any competition data to any party not participating in the Competition (this includes uploading the data to any public site such as Kaggle or GitHub). You may upload, store and work with the data on any cloud platform such as Google Colab, AWS or similar, as long as 1) the data remains private and 2) doing so does not contravene Zindi’s rules of use.

You must notify Zindi immediately upon learning of any unauthorised transmission of or unauthorised access to the competition data, and work with Zindi to rectify any unauthorised transmission or access.

Your solution must not infringe the rights of any third party and you must be legally entitled to assign ownership of all rights of copyright in and to the winning solution code to Zindi.

Submissions and winning

You may make a maximum of 5 submissions per day. Your highest-scoring solution on the private leaderboard at the end of the competition will be the one by which you are judged.

Zindi maintains a public leaderboard and a private leaderboard for each competition. The Public Leaderboard includes approximately 50% of the test dataset. While the competition is open, the Public Leaderboard will rank the submitted solutions by the accuracy score they achieve. Upon close of the competition, the Private Leaderboard, which covers the other 50% of the test dataset, will be made public and will constitute the final ranking for the competition.

If you are in the top 20 at the time the leaderboard closes, we will email you to request your code. On receipt of email, you will have 48 hours to respond and submit your code following the submission guidelines detailed below. Failure to respond will result in disqualification.

If your solution places 1st, 2nd, or 3rd on the final leaderboard, you will be required to submit your winning solution code to us for verification, and you thereby agree to assign all worldwide rights of copyright in and to such winning solution to Zindi.

If two solutions earn identical scores on the leaderboard, the tiebreaker will be the date and time in which the submission was made (the earlier solution will win).

The winners will be paid via bank transfer, PayPal, or other international money transfer platform. International transfer fees will be deducted from the total prize amount, unless the prize money is under $500, in which case the international transfer fees will be covered by Zindi. In all cases, the winners are responsible for any other fees applied by their own bank or other institution for receiving the prize money. All taxes imposed on prizes are the sole responsibility of the winners.

You acknowledge and agree that Zindi may, without any obligation to do so, remove or disqualify an individual, team, or account if Zindi believes that such individual, team, or account is in violation of these rules. Entry into this competition constitutes your acceptance of these official competition rules.

Please refer to the FAQs and Terms of Use for additional rules that may apply to this competition. We reserve the right to update these rules at any time.

Reproducibility

If your submitted code does not reproduce your score on the leaderboard, we reserve the right to adjust your rank to the score generated by the code you submitted.
If your code does not run you will be dropped from the top 10. Please make sure your code runs before submitting your solution.
Always set the seed. Rerunning your model should always place you at the same position on the leaderboard. When running your solution, if randomness shifts you down the leaderboard we reserve the right to adjust your rank to the closest score that your submission reproduces.
We expect full documentation. This includes:
- All data used

- Output data and where they are stored

- Explanation of features used

- Your solution must include the original data provided by Zindi and validated external data (no processed data)

- All editing of data must be done in a notebook (i.e. not manually in Excel)

Data standards:

Your submitted code must run on the original train, test, and other datasets provided.
If external data is allowed it must not exceed 1 GB. External data must be freely and publicly available, including pre-trained models with standard libraries. If external data is allowed, any data used should be shared on the discussion forum.
Packages:
- You must use the most recent versions of packages. Custom packages in your submission notebook will not be accepted.

- You may only use tools available to everyone i.e. no paid services or free trials that require a credit card.

Consequences of breaking any rules of the competition or submission guidelines:

First offence: No prizes or points for 6 months. If you are caught cheating all individuals involved in cheating will be disqualified from the challenge(s) you were caught in and you will be disqualified from winning any competitions or Zindi points for the next six months.
Second offence: Banned from the platform. If you are caught for a second time your Zindi account will be disabled and you will be disqualified from winning any competitions or Zindi points using any other account.
Monitoring of submissions

We will review the top 20 solutions of every competition when the competition ends.
We reserve the right to request code from any user at any time during a challenge. You will have 24 hours to submit your code following the rules for code review (see above).
If you do not submit your code within 24 hours you will be disqualified from winning any competitions or Zindi points for the next six months. If you fall under suspicion again and your code is requested and you fail to submit your code within 24 hours, your Zindi account will be disabled and you will be disqualified from winning any competitions or Zindi points.
Further updates and rulings of note:

Multiple accounts per user, collaboration or membership across multiple teams are not allowed.
Code may not be shared privately. Any code that is shared, must be made available to all competition participants through the platform.
Solutions must use publicly-available, open-source packages only, and all packages must be the most updated versions.
Solutions must not infringe the rights of any third party and you must be legally entitled to assign ownership of all rights of copyright in and to the winning solution code to Zindi.
You will be disqualified if you do not respond within the timeframe given in the request for code.
We reserve the right to update these rules at any time.

Other rules can be found here

https://zindi.africa/competitions/akeed-restaurant-recommendation-challenge

<img src="../Train.png" alt="alt text" width="1000"/>



