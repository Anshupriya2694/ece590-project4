# ece590-project4

![](55354483-bae7af80-547a-11e9-9909-a5621251065b.png)

Replication of a serverless application for this project. Created a lamba application called **publisherApp**. This application uses cloud watch event triggeres every minute to get the required data from dynamoDB. It is picking data from the DB and putting it an SQS Queue called **producer**

The 2nd lambda application is called **consumerApp**. This has an event based trigger on the SQS called **producer**. This function gets wikipedia information about the company and calls the AWS's sentiment analysis APIs to find the sentiment and entity from the company namr in the producer queue.

Finally, the result is published onto an S3 bucket called fangsentiment-as996 as a csv file. 
