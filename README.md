# Overview
This project explores and analyzes food establishment ratings across the United Kingdom using MongoDB and Python. It involves database setup, updates, and exploratory analysis to extract meaningful insights from the data.

## Project Structure
* **NoSQL_analysis_starter.ipynb:** Jupyter Notebook containing scripts for exploratory data analysis.
* **NoSQL_setup_starter.ipynb:** Jupyter Notebook for database setup and updates.
* **Resources Folder:** Contains the establishments.json file with the dataset used for analysis.

## Workflow

### Part 1: Database and Jupyter Notebook Set Up
The NoSQL_setup_starter.ipynb notebook is used for this section:
    * Data Import-  The data in the establishments.json file has been imported from the Terminal. The database is named **uk_food** and the collection is called **establishments**. The command used for import is:
        **mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json**
    * Initial setup:
       * Required libraries (PyMongo and pprint) were imported.
       * A MongoDB client instance was created to interact with the database.
    * Verification:
       * Listed all databases to confirm uk_food is created.
       * Listed collections to ensure establishments is present.
       * Displayed a sample document from the collection using find_one() and pprint.
       

### Part 2: Database Updates
The NoSQL_setup_starter.ipynb notebook was also used for database updates:

Adding a New Establishment:
1. A new establishment, "Penang Flavours," was added to the database with the following details:
   
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

3.  Updating BusinessTypeID:
    * Queried for the BusinessTypeID corresponding to "Restaurant/Cafe/Canteen" and updated the new establishment accordingly.
4.  Removing Establishments in Dover:
    * Counted the documents associated with the "Dover" Local Authority.
    * Deleted these records and verified their removal.
5.  Data Type Conversion:
    * Converted latitude and longitude fields to decimal numbers.
    * Converted RatingValue to integers, ensuring non-numeric values were coerced to null beforehand.

### Part 3: Exploratory Analysis
The NoSQL_analysis_starter.ipynb notebook was used for analyzing the data. Key analyses performed:
1. Establishments having a hygiene score equal to 20.
2. Establishments in London having a RatingValue greater than or equal to 4. 
3. The top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score and nearest to the new restaurant added, "Penang Flavours". 
4. The geocode was compared to find the nearest locations. Search was made within 0.01 degree on either side of the latitude and longitude.
5. Establishments in each Local Authority area having a hygiene score of 0. The results were sorted from highest to lowest, and the top ten local authority areas were printed out.

## Technologies Used
* Database: MongoDB
* Programming Language: Python
* Libraries: PyMongo, pprint
* Tools: Jupyter Notebook

## How to Run

* Ensure MongoDB is installed and running on your system.
* Import the data into MongoDB:
    mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json
* Open the Jupyter notebooks to explore the setup and analysis.
* NoSQL_setup_starter.ipynb for database setup and updates.
* NoSQL_analysis_starter.ipynb for exploratory analysis.


