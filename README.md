# twittersearch--COVID19
Here is my second work as a Data Engineer for searching people who use #COVID19 on their tweets. 
My post gives a thorough explanation of how to set up the code (including the dependancies), what it's doing, and an example how to use the resulting tweet data. I've also included the basics below.

This program will search for tweets and save them to a .JSON formatted file. Twitter limits the amount of tweets that can be downloaded per 15 minutes; as such, when an exception is raised (i.e., the maximum allowed number of tweets has been reached) the script will pause for 15 minutes and then continue.

A user-contributed resource is available here with additional information on reading and extracting information from the .JSON file using Python.
Dependencies

To access the Twitter API I used Tweepy 3.5.0. I also imported the libaraies: json, datetime, time, os and sys.

In addition, you'll need a personal Twitter "data-mining" application (which is very easy to set up). I used this guide to register my app. You will need to register your own in order to generate a consumer key, consumer secret, access token, and access secret; these are required to authenticate the script in order to access the Twitter API.
Running the script

    Save the python file or download/clone the repository to your local machine. Make sure you have the dependencies.

    Open the twitter_search.py file and then find the load_api() function (at the top) and add your consumer key, consumer secret, access token, and access secret. For example:

    consumer_key = '189YcjF4IUzF156RGNGNucDD8'
    consumer_secret = 'd7HY36s4pSh03HxjDg782HupUjmzdOOSDd98hd'
    access_token = '2543812-cpaIuwndjvbdjaDDp5izzndhsD7figa9gb'
    access_secret = '4hdyfnas7d988ddjf87sJdj3Dxn4d5CcNpwe'

#this API key are not usable, u can have your own API by requesting on twitter developers.

       Go to the main() function and edit the search criteria. Namely, you should enter a search phrase, the maximum time limit for the script to run, and the date range for the search (relative to today). For example:
    search_phrase = '#COVID19' #OR SOMETHING ELSE
    time_limit = 1.0 # runtime limit in hours
    min_days_old, max_days_old = 1, 2 # search limits

    # e.g. min_days_old, max_days_old = 7, 8
    # gives the current weekday from last week,
    # min_days_old=0 will search from right now



Open the terminal/command line to the file location and type:

python twittersearch.py

The script will run until all tweets within your search criteria have been found.

I got my permission to using this soruce of code by Copyright (c) 2016 Alexander Galea.
