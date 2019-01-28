# NLP2SQL

NLP2SQL is a platform that allows you to use natural language to SQL queries that run autonomously.

# NLP to SQL

This project aims to create an API that allows a user to interact with an SQL database in a natural way through speech or text.

## Description

Our API will serve as a wrapper to a user's database.
Once connected, the program will analyze the database structure (existing tables) and create the necessary mappings. With these, a user can interact with their database through natural speech or text.

### Examples

* How many clients bought our products last month?
* Which student had the highest average in the last quiz?
* Remove employee 12.

## Technology Stack

* Natural Language Processing - Python NLTK
* Speech to text API - TBD
* Command Line Interface - Python
* Database Control - SQL

## Detailed Functionality

Following is a description of the full functionality we aspire our API to implement.

### Installation

Our program should be installable with pip from the official Python Package Index. This makes it incredibly simple for our program to be distributed and installed for users.

### Initialization

Upon running the program for the first time they will go through initialization.

It will ask for the database credentials to be able to analyze the database structure.
The program will also need to be pointed to the location of the database whether it is local or hosted elsewhere in which case it might ask for further authentication information.

### Database Analysis

Once the database is located, we need to analyze it's structure to create our NLP to SQL mappings.

This will run a predefined set of queries to obtain a list of existing tables, entities, and relations.

We could then use these tokens as a dataset for a machine learning algorithm which would enable more fluid communication.
For example, if a preschool database has a "Student" entity, we should be able to look there when a user queries the database for information on "Children".

### Main Event Loop

The user can communicate with it in various ways:

* Text - command line interface
* Voice - Connected recording device
* Audio - A prerecorded file could be parsed

If the input is verbal we will use a speech recognition API to parse it into text, our current candidate is Google's offering. The text will then go through the NLTK library to be tokenized and analyzed for meaning and intent.

We then match these tokens with our database mappings either directly or tangentially ("children" -> "Students") to understand which entities we need to interact with.

Finally, with the deduced intent and matched tokens we can build the proper SQL query to send to the database.

The results are then displayed to the user.

### Two Way Interaction

All throughout the main event loop, our API will be able to respond with relevant warnings and errors, but also suggestions and requests for further actions.

This could arise when a user wants to run an action they might not have the permissions to do such as viewing particular data, then the API could inform the user or prompt them for further authentication.
