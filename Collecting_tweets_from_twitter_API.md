Following are the steps on setting up Twarc and scraping tweets

## Install Tawrc library

Twarc is a command line tool (python library) for performing full archival search and retrieval of the twitter. It allows us to use various parameters to filter the records we retrieve from the twitter API. The full documentation of Twarc could be found here: https://twarc-project.readthedocs.io/en/latest/windows10/

The prerequisites for setting-up Twarc in your system are
#### 1. Python installed on your system 
Run following command on your Command Line Tool (Command Prompt OR Powershell OR Windows Terminal) to check whether python is installed in your system or not. If it is installed in your system, it should result the python version you have installed.
    
    python --version
#### 2. Twitter Developer account with registered app, api keys and bearer token
You can apply for a twitter developer account from the Twitter Developer platform by accessing the following link : https://developer.twitter.com/en
  
    
Once you have fulfilled the prerequisites above, twarc can be installed using a simple command on your command line tool (Command Prompt OR Powershell OR Windows Terminal). Following command should be run on the command line tool to install Twarc2

    pip install --upgrade twarc





## Setup bearer token in your environment
Once the twarc library is installed in your system, the next step is to add the bearer token to your system which enables you to perform the archival search from the twitter API. To add bearer token run the following command on your command line tool.

    twarc2 configure
    
You will be asekd to enter the bearer token which can be found/generated on your developer portal. For full archival search, entering other tokens are optional so you can skip it.

## Execute the script to scrape the tweets(in JSON format)

To get the historical tweets, we will be using various parameters in our scraping script to filter the records. We can add/remove the filter options based on our need. IN this example, we will be scraping tweets based on the following parameters.

1. Start Time
2. End Time
3. Search Type (Archival or Not)
4. HashTags
5. Place
6. Retweets or Not

````
twarc2 search --start-time 2010-01-01 --end-time 2022-07-01 --archive "(#leisure OR #travel OR #fun OR #vacation OR #nature OR #lifestyle OR #summer OR #tourism OR #recreation OR #outdoors OR #photography OR #beach OR #sky OR #adventure OR #love OR #holiday OR #people OR #photooftheday OR #design OR #happy OR #landscape OR #fashion OR #instagood OR #luxury #water OR #tree OR #hotel OR #instatravel OR #business OR #fitness OR #holiday OR #matchday OR #match OR #sun) place_country:gb" final.json
````
Below is another example:

````
twarc2 search --start-time 2017-01-01 --end-time 2022-10-01 --archive "(#leisure OR #travel OR #fun OR #vacation OR #nature OR #lifestyle OR #summer OR #tourism OR #recreation OR #outdoors OR #photography OR #beach OR #adventure OR #holiday OR #photooftheday OR  #happy OR #landscape OR #fashion OR #instagood OR #luxury OR #hotel OR #business OR #fitness OR #movie) place_country:gb has:geo -is:retweet" tweets.json
````

## Convert the JSON file into CSV

Once we get the data required in the JSON format, we then need to convert it to CSV format as it can be loaded to a dataframe and analyzed easily. To convert our JSON output to CSV, we can use twarc-csv library which can be installed using the following command.

````
pip3 install --upgrade twarc-csv
````

Once it is installed, run following command to convert the JSON file to CSV.

````
twarc2 csv tweets_json_file.json tweets_csv_file.csv
````

## Validate the result
