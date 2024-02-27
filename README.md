# Apache_Spark_Assigment

- The purpose of this assignment is to get hands on experience of Apache Spark on real world dataset.
- Deployed a 4 node Hadoop cluster using AWS EMR (Elastic Map Reduce) service and configured Apache Spark to run on this cluster.
- Cluster Configuration:
  - 1 Master node with m4.xlarge instance - 4C/16GB
  - 3 Slave nodes with m4.large instances - 2C/8GB

# Used the above cluster to perform feature extraction tasks as below,

# Task 1: Read the data
- 1) Read RAW_recipes.csv from S3 bucket. link- 's3a://raw-recipes-clean-upgrad/RAW_recipes_cleaned.csv'
- 2) Ensure each field has the correct data type.

# Task 2: Extract individual features from the nutrition column.
- The nutrition column is read as a string when it should be an array of float values. Each row in the nutrition column contains seven values. Each value represents nutrition information.
- Your task is to separate the array into seven individual columns.

![image](https://github.com/devendra2595/Apache_Spark_EDA/assets/116253033/99936223-9fcb-4bcb-95f9-a6ce48ae4d63)


# Task 3: Standardize the nutrition values.
- The nutritional values in absolute terms will have a lot of variation. For example, a recipe serving six people (recipe A) will have more sugar than a recipe meant to serve one person (recipe B). 
But that does not necessarily imply that the sugar per person in recipe A is more than in recipe B. 

- Standardize the nutrition values. Convert the nutritional values to per 100 calories.

# Task 4: Convert the tags column from a string to an array of strings.
- Consider a data point from the tags column.
  ![image](https://github.com/devendra2595/Apache_Spark_EDA/assets/116253033/463416ea-6d2c-4eb5-9739-af89c62160b4)

# Task 5: Read the second data file
- Read the RAW_interaction.csv. link - 's3a://raw-interactions-upgrad/RAW_interactions_cleaned.csv'
- join this interaction level file with the recipe level dataframe.
- The resulting data frame should have all the interactions.


# Task 6:  Create time-based features.
- Create features that capture the time passed between one review and the date on which the recipe was submitted.
