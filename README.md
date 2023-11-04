Description of the project:
1. For this project, we use a spark based MapReduce Algorithm to generate a Friend Recommendation System.
2. Firstly, we split the lines in the dataset on the basis of the tab character "/t". In this way, we get the list of friends for each friend.
3. Now, we use flatMap to generate a list of mutual friends for a pair of friends.
4. Next we calculate the count of mutual friends between the two friends in a pair using reduceByKey.
5. Now, we create a new RDD where we separate out each pair of friends such as (0,1),(0,2),(0,3),... etc.
6. We do a left join between the newly created RDD and the count of mutual friends.
7. Now, in the final setp, we start with filtering out the recommendations where the user is already friends with the recommended friend and then sort out the recommendations based on the count of mutual friends.
8. Finally, we select the top 10 recommendations for a particular user and store it in the form of (user,[top_recommendations]).

Note:
    a. This project was done in a Databricks cluster.