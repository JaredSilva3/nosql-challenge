# Eat Safe, Love Database Analysis

## Overview
This project explores data on UK food establishments using MongoDB and Python. We set up the database, update records, and analyze hygiene scores and ratings to understand trends.

## Requirements
- **MongoDB** 
- **Python** with:
  - `pymongo`
  - `pandas`

## Steps

### Part 1: Database Setup
1. **Import Data**: Load `establishments.json` into a MongoDB database called `uk_food`, in a collection named `establishments`.
2. **Connect to MongoDB**: Use `MongoClient` in the notebook to connect to MongoDB.
3. **Verify**:
   - Check that the database and collection loaded correctly.
   - Preview a document to confirm.

### Part 2: Update the Database
1. **Add a New Entry**: Insert a new restaurant, "Penang Flavours."
2. **Find and Update `BusinessTypeID`**: Retrieve and update the `BusinessTypeID` for "Restaurant/Cafe/Canteen."
3. **Remove Records**: Delete all records with `LocalAuthorityName` set to "Dover."
4. **Convert Data Types**:
   - Change latitude and longitude to decimals.
   - Set `RatingValue` fields as integers.

### Part 3: Analysis
1. **Hygiene Score Check**:
   - Find establishments with a hygiene score of 20.
   - List high-rated establishments in London.
2. **Nearby Search**:
   - Locate the top 5 establishments near "Penang Flavours" with a `RatingValue` of 5, sorted by hygiene score.
3. **Aggregate Data**:
   - Show the top 10 local authorities with the most establishments having a hygiene score of 0.

### Import Data
```bash
mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray

## Summary
- Local authorities with the most establishments scoring 0 in hygiene are identified.
- The proximity search finds the top 5 nearby establishments to “Penang Flavours” by hygiene score.
- DataFrames provide a clear view of analysis results.