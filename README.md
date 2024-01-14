I created an app that leverages AWS services to automate the process of summarizing text data using Amazon Bedrock's generative AI foundation model, "Anthropic Claude". 
To achieve this, I first codeed a lambda function in python to accept an input file and generate a summary text in S3 bucket, by passing the input file to Gen AI model of my choice, which is "Anthropic Claude".
I then configured an API in API gateway and integrated it with the aforementioned lambda function.

The flow of execution/architecture is shown below:

![image](https://github.com/whoisdeepak/AmazonBedrock-TextSummarizationApp/assets/101911034/bfb366d0-6ad6-48c8-8962-244c7e37d68c)

The workflow involves making a POST request to an API Gateway, which triggers a Lambda function. 
The Lambda function, implemented in Python, then interacts with Anthropic Claude to analyze an input text file and generate a concise summary. 
The resulting summary is then saved to an S3 bucket for easy access and reference.

Repository contains a file named "Input_MeetingTranscript.txt" which contains the entire transcript of a fictional meeting taking place at Tesla.
When this file is sent as input to API gateway, the generative AI model and my lambda code work together to create a summary of this meeting transcript and saves it to S3.
The summary generated in my project can be viewed in the file named "summarized output.txt"

This generative AI model is not just limited to text summarization, but one can have conversational dialogue with it, asking different kinds of details about the meeting/input file.
