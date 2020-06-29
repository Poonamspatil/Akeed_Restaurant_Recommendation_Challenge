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
|A7B8IGM X 0 X 105      |     0
|NS70FA9 X 0 X 105      |      1
|WTWOE69 X 0 X 105      |      0

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
