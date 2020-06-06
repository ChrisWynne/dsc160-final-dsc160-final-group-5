# Something Political

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

To present our results, we'll be personally looking at various generated responses from our GPT2 model when trained on left, right, and centrist points of view. Originally, we wanted to post to Reddit to quantitatively identify how well our responses fared among strangers, but given the current complicated political situation we decided against it. Instead, we opted to send prompts and generated responses to people we know and then inform them after the fact that the responses were artificially generated. We believe our project is interesting because it has the potential to show the main talking points of left, right, and centrist political views. 

<s>/*
We’ll generate text for thread names and comments and then post them onto Reddit to evaluate how they fare quantitatively in regards to upvotes, downvotes, and overall thread activity. We anticipate running into issues when posting our outputs to Reddit subreddits as the results could be construed as satire and may get the bot banned. To extend on ideas from lectures, our project will feed our outputs back into r/PoliticalDiscussion and see what kind of political bias is generally perceived. We believe our project is interesting because it will show what happens when you combine two polar opposite political views. 
*/</s>

We’ll be referencing the following papers/ sites in the creation of our project:

How to use GPT-2:
https://www.gwern.net/GPT-2

Article about bots used in politics:
https://www.tandfonline.com/doi/full/10.1080/19331681.2018.1448735

Article about bots posing as humans:
https://www.topbots.com/can-bots-manipulate-public-opinion/

How GPT-2 performs when trained on Reddit data:
https://www.reddit.com/r/SubSimulatorGPT2/


## Data and Model

(10 points) 

The data we used was scraped from the subreddits r/Republican and r/Democrats. We scraped posts with more than 5 comments and removed the phrases "deleted" and "I am a bot". This was to help remove irrelevant data to feed to our model, since the out model, the 124M GPT-2 architecture, limits our dataset to 1 MB. We have 3 1-MB training datasets and three different models. One is trained on only data from r/Democrats, one is trained on only data from r/Republicans, and the last is trained on equal amounts of both. We have given these models names as the output they great is "human". Their names are Carlisle (Republican), Creighton(Democrat), and Kuzco(Both).
  - [https://github.com/ucsd-dsc-arts/dsc160-final-dsc160-final-group-5/tree/master/data/matt_results] (training text files).
  - [https://minimaxir.com/2019/09/howto-gpt2/] (article describing GPT-2 and the tool we used to train it). 

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

### Additional Libraries:

GPT-2 Tool:
https://github.com/minimaxir/gpt-2-simple

Tensorflow Version:
1.15

Pushshift API (for Reddit scraping): 
https://pypi.org/project/psaw/

 - Pandas
 - Numpy
 
 Additional Notes:
 
 For loading a saved local model, you need to have a local version of gpt-2-simple and the local model data. 
 This model data is too large to fit on the github repo, so we have included a link to a google drive file with both the modified library code and the local models. These files should be in the same parent directory as this repository.
Here is the link: https://drive.google.com/file/d/11U_56F8S0ZdDexSjvb8Vsgy4CU8Plb9S/view?usp=sharing

## Reference
How to use GPT-2:
https://www.gwern.net/GPT-2

Article describing GPT-2 and the tool we used to train it:
https://minimaxir.com/2019/09/howto-gpt2/ 

Article about bots used in politics:
https://www.tandfonline.com/doi/full/10.1080/19331681.2018.1448735

Article about bots posing as humans:
https://www.topbots.com/can-bots-manipulate-public-opinion/

How GPT-2 performs when trained on Reddit data:
https://www.reddit.com/r/SubSimulatorGPT2/

