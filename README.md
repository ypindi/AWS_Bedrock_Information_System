# AWS Bedrock, AWS Lex, AWS Connect, AWS Cloudfront and Slack Information Chatbot and Call Centre

## 1 Introduction
OEV Online Dienste GmbH, for whom this project was developed for,
currently lacks a centralized and user-friendly
communication system to effectively address inquiries and facilitate interactions with
stakeholders through chat or mobile phone. 
This was achieved through the use of a Chatbot using Slack and a centralized automated telephone number using Amazon Connect
which give you all information about OEV for both employees and external stakeholders visiting OEV's website.

## 2 Process
Both the internal employees of the organization as well as external stakeholders visiting the OEV Online Dienste GmbH are benefitted through this project.
An external stakeholder can call the centralized telephone number and ask any information regarding OEV (eg. address, CEO, 
work at OEV, and other general information). The same thing can also be done through a chatbot present in the internal Slack app available to employees
regarding the same information.

Amazon Cloudfront hosts the chatbot through which you can either chat or make voice requests. 
There is also a telephone line number to call up for the same requests.
Whenever a user makes a request on the chatbot or telephone line, a request is made to Amazon Connect, which is connected to Amazon Lex.
Amazon Lex is a fully managed artificial intelligence (AI) service with advanced natural language models to deploy conversational interfaces in applications.
Amazon Lex processes the request and sends a request to Amazon Bedrock, which is another application for deploying Generative AI models. It has a knowledge base which stores all the
information about OEV in a vector database. Based on the request, the appropriate data is sent back to AWS Lex, which sends it back to Amazon Connect, which again sends the requested data
to the chatbot or the telephone line.

Slack is the internal app for communication within the organization. Any requests through the Slack bot are directed to Amazon Lex, and the same process takes place.
Amazon Lex requests information from Amazon Bedrock, which then based on its information from its vector database, sends the information back to Amazon Lex, which redirects the information
to the Slack channel.

Amazon S3 stores necessary data, which is fed to Amazon Bedrock for creating the vector database.
Amazon Bedrock serves as the knowledge base,
processing this data for accurate responses. Amazon Lex provides a conversational
interface for text and voice interactions, linked to Amazon Connect for managing voice
requests. Slack integration ensures timely notifications, and the telephone call feature adds
convenience to external stakeholders. This system delivers high availability, security, and flexibility, making it an
efficient solution for OEV.

## 3 Architecture
The architecture of the entire project done on AWS is below:
```
https://github.com/ypindi/AWS_Bedrock_Information_System/blob/main/Pictures/Architecture_AWS_Unified_Messaging_Bot.png
```
![AWS Project](https://github.com/ypindi/AWS_Bedrock_Information_System/blob/main/Pictures/Architecture_AWS_Unified_Messaging_Bot.png)

## 4 Working Videos
The working videos are located here: 
[Videos](https://github.com/ypindi/AWS_Bedrock_Information_System/tree/main/Videos)
```
https://github.com/ypindi/AWS_Bedrock_Information_System/tree/main/Videos
```
