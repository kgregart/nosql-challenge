# nosql-challenge

![food](https://github.com/kgregart/nosql-challenge/blob/main/Images/food.jpg)

# Background

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

# Instructions

## Part 1: Database and Jupyter Notebook Set Up

1. Import the data provided in the establishments.json file.

2. Import the libraries: PyMongo and Pretty Print (pprint).

3. Create an instance of the Mongo Client.

4. Confirm the database was created and loaded properly:
    
    - List the databases in MongoDB. Confirm that uk_food is listed.
    - List the collection(s) in the database to ensure that establishments is there.
    - Find and display one document in the establishments collection using find_one and display with pprint.

5. Assign the establishments collection to a variable to prepare the collection for use.

## Part 2: Update the Database

The magazine editors have some requested modifications for the database. Make the following changes to the establishments collection:

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. Add the following information to the database to include in the analysis:

    {
        "BusinessName":"Penang Flavours",
        "BusinessType":"Restaurant/Cafe/Canteen",
        "BusinessTypeID":"",
        "AddressLine1":"Penang Flavours",
        "AddressLine2":"146A Plumstead Rd",
        "AddressLine3":"London",
        "AddressLine4":"",
        "PostCode":"SE18 7DY",
        "Phone":"",
        "LocalAuthorityCode":"511",
        "LocalAuthorityName":"Greenwich",
        "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
        "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
        "scores":{
            "Hygiene":"",
            "Structural":"",
            "ConfidenceInManagement":""
        },
        "SchemeType":"FHRS",
        "geocode":{
            "longitude":"0.08384000",
            "latitude":"51.49014200"
        },
        "RightToReply":"",
        "Distance":4623.9723280747176,
        "NewRatingPending":True
    }

2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

3. Update the new restaurant with the BusinessTypeID found.

4. The magazine is not interested in any establishments in Dover.  Identify how many documents contain the Dover Local Authority and remove any establishments within the Dover Local Authority from the database. Then check the number of documents to ensure they were deleted.

5. Some of the number values are stored as strings, when they should be stored as numbers.

    - Use update_many to convert latitude and longitude to decimal numbers.
    - Use update_many to convert RatingValue to integer numbers.

## Part 3: Exploratory Analysis

Eat Safe, Love has specific questions, which will help them find the locations they wish to visit and avoid.

1. Which establishments have a hygiene score equal to 20?

    ![Q1](https://github.com/kgregart/nosql-challenge/blob/main/Images/Q1.png)
   

2. Which establishments in London have a RatingValue greater than or equal to 4?

    ![Q2](https://github.com/kgregart/nosql-challenge/blob/main/Images/Q2.png)

   _Note:  Partial results shown_
   

3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

    ![Q3](https://github.com/kgregart/nosql-challenge/blob/main/Images/Q3.png)

      _Note:  Partial results shown_
   

4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

    ![Q4](https://github.com/kgregart/nosql-challenge/blob/main/Images/Q4.png)
