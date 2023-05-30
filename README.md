# nosql-challenge
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

# Set Up

Using mongosh in Terminal, you will need to import the 'establishment.json' file from 'Resources' using the below code:

    `mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json`

# Running NoSQL_setup_starter

You will then be able to run the 'NoSQL_setup_starter.ipynb' code which will create a MongoClient instance before checking that all databases & collections are working according to the import done with mongosh and assign a variable ('establishments') to the collection 'establishments'.

After this, the code will update the database with a new restaurant "Penang Flavours", and update the information for this restaurant by searching for the 'BusinessTypeID' and 'BusinessType' to confirm what 'Penang Flavours' belongs to.

The code will then check to see if any 'LocalAuthorityName' shows "Dover" and then deletes those documents as per the magazine's requirements to not cover Dover.

Lastly, all geocodes are updated from string to decimal for both latitude & longitude.

# Running NoSQL_analysis_starter
After running the 'NoSQL_setup_starter.ipynb' code, you will then be able to run the 'NoSQL_analysis_starter.ipynb' code which will again create a MongoClient instance before checking all databases & collections are working and assign a variable ('establishments') to the collection 'establishments'.

After this, the code performs exploratory analysis to answer the 4 below questions:

    1. Which establishments have a hygiene score equal to 20?
    2. Which establishments in London have a RatingValue greater than or equal to 4?
    3. What are the top 5 establishments with a RatingValue of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
    4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

Each result will deliver a pandas DataFrame to show all establishments that meet the criteria listed.