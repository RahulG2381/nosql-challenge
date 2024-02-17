# Instructions
The purpose of this report is to document the steps taken to evaluate and analyse food hygiene ratings data for various establishments across the United Kingdom. The evaluation is conducted to assist the editors of the food magazine, Eat Safe, Love, in making informed decisions for their future articles.
# Part 1: Database and Jupyter Notebook Set Up
## Import Data and Set Up Database
To begin the analysis, I used the NoSQL_setup_starter.ipynb  file  and provided establishments data was imported into a MongoDB database named "uk_food," with a collection named "establishments." The import was performed using the establishments.json file. The steps taken in the Terminal are as follows:
### mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray
## In jupyter Notebook  following steps were taken:
1.	import all the required libraries : PyMongo, pandas, and Pretty Print (pprint).
2.	Create an instance of the Mongo Client.
3.	Confirm that the database has been created and loaded the data properly:
-	List the databases you have in MongoDB. Confirm that uk_food is listed.
-	List the collection(s) in the database to ensure that establishments is there.
-	Find and display one document in the establishments collection using find_one and display with pprint.
4.	Assign the establishments collection to a variable to prepare the collection for use.
# Part 2: Update the Database
The database required modifications as per the instructions provided. 
The updates included    
1.	Adding a new halal restaurant, "Penang Flavours," and ensuring the correct BusinessTypeID was assigned. 
2.	Finding the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields
3.	Update the new restaurant with the BusinessTypeID you found
4.	Removed any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
5.	number values stored as strings were converted to numbers using the update_many method.
# Part 3: Exploratory Analysis
The final section involved exploring the dataset and answering specific questions posed by Eat Safe, Love magazine. I sued the NoSQL_analysis_starter.ipynb for this section of the challenge. The questions were addressed using a combination of MongoDB queries and Pandas DataFrames in Jupyter Notebook.
Following questions were used to explore the database and found the answers for the magazine editors.
1.	Which establishments have a hygiene score equal to 20?
2.	Which establishments in London have a RatingValue greater than or equal to 4? I used  $regex as part of my search.
3.	What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? search establishments within 0.01 degree on either side of the latitude and longitude.
4.	How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest and print out the top ten local authority areas.
