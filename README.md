# Project Title

DSC160 Data Science and the Arts - Final Project - Generative Arts - Spring 2020

Project Team Members: 
- Andy Do, ando@ucsd.edu
- Saieashwar Mukund, samukund@ucsd.edu
- Chase Oden, coden@ucsd.edu
- Matthew Widjaja, mwidjaja@ucsd.edu
- Chris Wynne, cwynne@ucsd.edu


## Abstract

(10 points) 

Our concept revolves around training a GPT-2 model on Reddit comments from conflicting political subreddits to possibly create a centrist view of politics. We’ll be using OpenAIs pretrained GPT2 model as a base, as well as use Pushshift for scraping from Reddit. Our training data will be sourced from subreddits on Reddit of conflicting political ideals, such as r/Republican and r/democrats. After training, we hope that our system will combine the views found in both polar different subreddits and somehow come out as a centrist view on the political views mentioned.

We’ll generate text for thread names and comments and then post them onto Reddit to evaluate how they fare quantitatively in regards to upvotes, downvotes, and overall thread activity. We anticipate running into issues when posting our outputs to Reddit subreddits as the results could be construed as satire and may get the bot banned. To extend on ideas from lectures, our project will feed our outputs back into r/PoliticalDiscussion and see what kind of political bias is generally perceived. We believe our project is interesting because it will show what happens when you combine two polar opposite political views. 

We’ll be referencing the following papers/ sites in the creation of our project:

How to use GPT-2
https://www.gwern.net/GPT-2

Article about bots used in politics:
https://www.tandfonline.com/doi/full/10.1080/19331681.2018.1448735

Article about bots posing as humans:
https://www.topbots.com/can-bots-manipulate-public-opinion/

How GPT-2 performs when trained on Reddit data:
https://www.reddit.com/r/SubSimulatorGPT2/


## Data and Model

(10 points) 

In the final submission, this section will describe both the data you use for this project and any pre-existing models/neural nets. For each you should provide the name, a textual description, and a link. If there is a paper (for neural net) link that as well.
- Such and such Neural Net. The short description of this neural net. 
  - [link to code]().
  - [Title of Paper with Link](). 
- Training data. Short description of training data including bibliographic info. [link to data]().

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- code for data acquisition/scraping
- code for preprocessing
- training code (if appropriate)
- generative methods

Link each of these items to your .ipynb or .py files within this seection, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

## Results

(30 points) 

This section should summarize your results and will embed links to documentation to significant outputs. This should document both process and show artistic results. This can include figures, sound files, videos, bitmaps, as appropriate to your generative art idea. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally innovative?
- How does your generative computational approach differ from traditional art/music/cultural production? 
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- What are the ethical concerns for this form of generative art? 
- In what future directions could you expand this work?

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

## Reference

All references to papers, techniques, previous work, repositories you used should be collected at the bottom:
- Papers
- Repositories
- Blog posts
