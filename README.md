# CartmanBot

# Repository Files
The followings are the file you can find in this repository and their descriptions.

README.md - Descriptions of contents of the repository

Module 5 - Capstone Project - Cartman Bot.ipynb - Module 5 final project's Google Colab notebook

Images - Collections of graphs and images produced during the project

Presentation.pdf - High-level presentation of methodology and recommendations for non-technical stakeholders

# Project Motivation
In this project, I developed a chatbot that mimics Eric Cartman, a character from the South Park animated series. The goal of this project is two fold -

1. To showcase the amazing capabilities of new Natural Language Processing models.
2. To create a fun chatbot with which we could enjoy chatting for entertainment.

# Project Process
My approach for this project is to follow the OSEMN framework. The steps of this framework is as follow - 

1. Obtain the data
2. Scrub the data
3. Explore the data
4. Model the data
5. Interpret the data

# Data Source
The primary data that I used in this project is the dialogues from the South Park Series. I found these dialogues in the transcripts secton of South Park Fandom page (https://transcripts.fandom.com/wiki/South_Park). To extract these dialogues and assign them to the correct characters, I used various html webscrapping techniques and store these values in a pandas dataframe.

# Data Scrubbing
Before training my model, I performed the following data scrubbing tasks on my dataframe - 
1. Removing rows with missing dialogues
2. Standardizing characters names (for example, converting Eric Cartman to Cartman)
3. Removing extra spaces in character names and dialogues
4. Removing scene descriptions that were included in the characters' dialogues

# Data Exploration
The following data exploration methods were also used to better understand the dataset - 
1. Investigate which characters speak the most in the series

![alt text](https://user-images.githubusercontent.com/29743560/93000567-49c57c00-f4f7-11ea-9f48-923b02c049f9.png)

2. Analyze which words Eric Cartman uses the most

![alt text](https://user-images.githubusercontent.com/29743560/93000558-48944f00-f4f7-11ea-8709-acf78a1056da.png)

3. Find out which characters Eric Cartman interacts with the most

![alt text](https://user-images.githubusercontent.com/29743560/93000566-49c57c00-f4f7-11ea-9ed2-6405f8368d72.png)

# Training the Model - Chatterbot Model
The first NLP model that I explored was Chatterbot. The result for this model can be seen below - 

![alt text](https://user-images.githubusercontent.com/29743560/93000563-49c57c00-f4f7-11ea-845c-05a7f6ebd32f.JPG)

Although this model captured typical Eric Cartman's lines, the output from the chatbot is not very responsive to the user's inputs.

# Training the Model - Microsoft DialoGPT
The second model that I used was Microsoft DialoGPT model which is based on OpenAI's GPT2 model and the Hugging Face PyTorch transformer. Before training this model, I converted the original dataframe in the way that every Cartman's line has 7 previous dialogues in the same row. The purpose is to create context around Cartman's lines. By creating context, our chatbot can response better to the user's inputs during the chat.

After training the model, I deployed the chatbot in a temporary chat app by using JupyterDash package. A few sample chats with CartmanBot can be seen below - 

![alt text](https://user-images.githubusercontent.com/29743560/93000560-492ce580-f4f7-11ea-898b-38df86f84437.JPG)
![alt text](https://user-images.githubusercontent.com/29743560/93000561-492ce580-f4f7-11ea-89a9-ad698678d675.JPG)
![alt text](https://user-images.githubusercontent.com/29743560/93000562-492ce580-f4f7-11ea-8a12-d07a904724ed.JPG)

# Areas for Improvements

The areas that I can work on in the future to improve the CartmanBot are -

- Utilized more complex NLP models such as GPT3
- Train the model for more Epochs
- The transcripts for some episodes are not available on Fandom's website. We can have more data to work with if we can add the lines from these episodes.
