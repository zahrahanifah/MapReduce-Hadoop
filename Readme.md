# Elon Musk Most Tweet About
I recently learned about Hadoop-MapReduce. 
On this repo, I'd like to share how to do partition on Elon Musk's Tweets using MRJob (MapReduce library in Python). In the end, We will get words within its counts, means we will know what is Elon Musk most tweet about!

#### Overview about the data : 
On this repo, we will use `data/clean_tweets.csv` . 
This file contains of tweet in row, and already clean from stopwords (e.g. a, The, is, are, etc), symbol (e.g. @, #, etc), and basic words/verb which I already removed using NLTK library 

(You can find how to use NLTK library and how to get `clean_tweets.csv` on this link -> https://github.com/zahrahanifah/TextAnalysis-with-NLTK )

## Download binary
- Download Apache Hadoop Binary : https://archive.apache.org/dist/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz
- Download Apache Spark Binary https://downloads.apache.org/spark/spark-3.3.1/

## Build Docker
1. If you are using Linux/MAC : run `./run_cluster.sh`
2. If you are using Windows : run `docker build -t hadoop-base:3.3.1 -f Dockerfile-hadoop . && docker-compose -f docker-compose-hadoop.yml up -d`

## How to run Local MapReduce
- There is `wordcount.py` python file in `map_reduce` directory
- You can run following command in yout terminal : `python3 map_reduce/wordcount.py data/clean_tweets.csv > output.csv`

## Running with Hadoop MapReduce
To run this file in Hadoop run this command `python3 map_reduce/ratings_breakdown.py -r hadoop --hadoop-streaming-jar /opt/hadoop-3.3.1/share/hadoop/tools/lib/hadoop-streaming-3.3.1.jar data/clean_tweets.csv > output.csv`

### Notes:
The output from this task still a bit messy (`output.csv`), it is still contain links (e.g. http) and some symbol. 


`#NeverStopLearning` is my current tagline, I'll come back to this repo to fix this later! `#datascience` `#dataengineering`
