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

The data we used was scraped from the subreddits r/Republican and r/Democrats. We scraped posts with more than 5 comments and removed the phrases "deleted" and "I am a bot". This was to help remove irrelevant data to feed to our model, since the out model, the 124M GPT-2 architecture, limits our dataset to 1 MB. We have 3 1-MB training datasets and three different models. One is trained on only data from r/Democrats, one is trained on only data from r/Republicans, and the last is trained on equal amounts of both. We have given these models names as the output they create is "human". Their names are Carlisle (Republican), Creighton (Democrat), and Kuzco (Both).
  - [https://github.com/ucsd-dsc-arts/dsc160-final-dsc160-final-group-5/tree/master/data/matt_results] (training text files).
  - [https://minimaxir.com/2019/09/howto-gpt2/] (article describing GPT-2 and the tool we used to train it). 

## Code

(20 points)

- scraping / preprocessing code: 

This code scrapes reddit posts/comments from the subreddits described above. All necessary install statements are present in the notebook. However, we have included the scraped data in the repo so it is not necessary to run this code. 

https://github.com/ucsd-dsc-arts/dsc160-final-dsc160-final-group-5/blob/master/code/tatami_scraping.ipynb

- training / generative methods code:

This is the code that trains the model and generates the text output (saving to a file). It takes a long time to train the model, but a local model and instructions for how to download/install the necessary libraries in the technical dependencies section at the bottom. However, if training on a GPU on datahub, it only takes around 10 minutes to run. Make sure to set is_local to false

https://github.com/ucsd-dsc-arts/dsc160-final-dsc160-final-group-5/blob/master/code/cwynne_gpt2.ipynb


## Results

### Prompt 1

>[title]
You say: "Police violence is problematic." - They hear: "I am fine with looting and arson." - You say: "I want criminal arsonists arrested." - They hear: "I want cops to break up peaceful protests and beat them up."<br/><br/>
[selftext]
Just a quick guide to what the other party understands from your positions. For your discussions and debates on this sub and elsewhere. I didn't come up with it, I merely translated it from memory. Can't find the original source, sorry.

<b>Creighton Model Response</b>

>[comment]You guys are so fucking stupid. If only we could just assume that the police state is real and that there’s some kind of collective punishment system.

This is a comment generated by the Democrat Creighton model which I would describe as heavy on the liberal left side of the political spectrum. The statement is very hyperbolic as it compares the U.S government response to the protests to police states. While the police response to the recent protest have been notably violent, they are a far cry from the full extent of an actual police state, which is comparable to what we have seen with North Korea's extreme supervision of its citizens or historically, Germany under the Nazi Regime and Italy under Benito Mussolini.

<b>Carlisle Model Response</b>

>[comment]I think we should focus on how we deal with crimes. All the illegals and all the crime that happens with the illegal immigrants.

This is an example of what I would call a very obvious Republican comment, and the model for these comments most likely supports President Trump (if it could). It’s quite intriguing to see how the model has been able to use the term "illegals", and the grievance voiced against what the comment calls illegal immigrants is a common shared point by supporters of Trump. Overall, this comment definitely feels like a Republican response.

<b>Kuzco Model Response</b>

>[comment]I don't think the rioters should be arrested
The rioters are not peaceful protestors. They are rioters.

Here, we definitely see some contradiction on the Kuzco model. This model was generated by learning from both sides, so we are expecting to see some contradiction in the texts generated. Here, the text starts off by stating that they do not believe that rioters should be arrested. Naturally, we’d expect the follow-ups to be defending their point, however the model generates “The rioters are not peaceful protestors. They are rioters.” Contradictory, this suggests that the rioters are violent (in which arresting them would be a solution).

### Prompt 2

>[title]
Will the death of George Floyd and the Flynn/FBI case delegitimize law enforcement for the majority of American voters?

>[subtext]
It seems like a unique news cycle over the past 30 days in the sense that police (federal and local) have lost a lot of trust from American voters on the right and the left. Most right leaning folks I know were outraged about the FBI case on Flynn, and left leaning folks I know are even more outraged by the killing of George Floyd. Even people on the right that I know say that the officer who killed George Floyd was clearly in the wrong. <br/><br/>
The question then I have is: what long term impacts will this have on the political legitimacy of law enforcement in the United States? What impacts, on both sides, will this have on the electorate? (Note, not just the 2020 election, but longer term tectonic shifts with the republican and democratic bases.)

<b>Creighton Model Response</b>

>[comment] I don't think the protests will have any lasting impact on the political system. The protests will continue to be about people who are doing something wrong and the government is corrupt.

This was a comment generated by our Democrat Creighton model. The response not only very clearly answers the question that was asked in the prompt, but also takes on the persona of a very pessimistic leftist in saying that these protests will have very little impact in the future if the same people are in office. It is a rather cynical outlook on current events and whether or not any progress will be achieved, but this matches with some of the views of left-leaning people during this trying time, since many have lost hope in our government. They believe that the actions of authorities and lack of accountability will continue on and protests will always occur with little to no progress.


<b>Carlisle Model Response</b>

>[comment] 
The President of the United States has a very specific responsibility to ensure that the police have the best possible equipment and training to deal with an individual in the event of a terrorist attack. The Democrats are the only one in the world that doesn't regard law enforcement as a legitimate federal agency. The system works and the criminal justice system is very fair and fairly run. As a citizen I am outraged by the way that the media sensationalizes this situation. It is a distraction that keeps the public at a distance. Let me just say that the media has become a total disgrace to the country. They are not covering the real issues that are being raised. You can do whatever you want and I will not be a Democrat anymore. And I will not be proud to be a Democrat. I still have friends and family that are Democrats.

This was a comment that was created by our Republican bot, Carlisle. This bot, interestingly enough, takes on the persona of a citizen who has recently shifted from a Democratic stance and moved to the Republican Party. This bot’s answer to the question in the prompt is that the events occurring now provide the world with a chance to change without the use of violence and force, but feels that the Democrats are not showing any regard for the law and are being fooled by the media. This response, along with many of the other Republican generated comments, highlights the idea that the Republican Party is censored and is only selectively given a voice as the media is not covering the real issues that should be aware to the public. It also is interesting to see the word terrorist, since it is a word that would be thrown around a lot in Republican discussion but has no place in this context. Lastly, but most importantly, it is interesting to see the bot defend the President and solely put blame on the media, the public that it has been lying to, and the Democrats. 

<b>Kuzco Model Response</b>

>[comment]
I think both sides are going to find a way to protect themselves. They both have a vested interest in removing republicans and democrats from power. Both are authoritarian and want to be as free as possible in order to control the world as they have been and keep power as they have been for the last 75 years.

Not surprisingly, many of the comments created by Kuzco, the bot trained on both Republican and Democratic views, are contradicting and confusing. This response, however, showed a true, middle-ground view that discredits both parties. Although the comment does not answer the question that was posed in the prompt, it does reflect a centrist view and points out that both sides will constantly have a common interest in overpowering the other side and gaining more traction with the public’s votes. However, the bot proceeds to call both sides authoritarian and essentially calls both parties regimes that want to control the country. This is an exaggeration that the bot could have generated from either partys’ comments that it was trained on, since both parties, at least in the case of reddit discussions, like to slight the opposing side’s views.

Kuzco honorable mention comments:

>The Left have always been the darkest and most hate-filled groups. But the Left is still the best.

>Trump is the Antichrist and the Democrats are the Antichrist. Both are corrupt and the only way to stop them is to unite and defeat them. You can't make a bad guy get elected.


### Prompt 3


>[title]<br/>
Did the world forget about Coronavirus?<br/>
[subtext]<br/>
Since when were gatherings of more than 50 people allowed? Wasn't everyone in the mainstream media condemning states that even thought about reopening just two weeks ago? Politicians not wanting to sacrifice even one life in exchange for the economy?<br/><br/>
Weren't reopening protestors made the laughing stock and the butt of everyone's joke, being labelled as a danger to everyone around them? Now we're multiplying those #s in enormous fashion, with thousands of people crowded and shouting together.<br/><br/>
How quickly the tune changes when agendas align. This just blatantly lays bare to me the hypocrisy of politicians and media moguls who hold no principle dear. We now even have medical experts saying it's perfectly OK to go out and protest, so long as it's for this cause.<br/><br/>
Could anyone enlighten me as to why this isn't just a blatant, transparent display of hypocrisy?<br/><br/>
Note: I fully support policy changes that will reduce police brutality, and justice for George Floyd. But I also can't ignore how quickly we've all just pulled a full 180 on our own principles and standards.


<b>Creighton Model Response</b>

[comment] lorem ipsum lorem ipsum

<b>Carlisle Model Response</b>

[comment] lorem ipsum lorem ipsum

<b>Kuzco Model Response</b>

[comment] lorem ipsum lorem ipsum

## Discussion

From our models and the various prompts they trained on we saw results that corresponded with what we expected given the training data of each model. The Democrat Creighton and Republican Carlisle models generated responses that were very much in line with their respective political parties, although we noted that they would express their points rather strongly. The combined Kuzco model unfortunately didn’t cohesively combine the left and right political views, and would instead tend to contradictory views of either side. On occasion the Kuzco model would generate something close to a Centrist view, but would generally view both left and right political parties in distinctly negative lights. 

Our results are culturally innovative because it shows some of the most popular approaches that people of the left and right political sides tend to have towards popular political discussion topics. Our generative approach is different from traditional cultural production because we aren’t just taking opinions off the internet and trying to match them to arbitrary prompts, but we’re synthesizing entirely new opinions based off of a large dataset of a single political ideal. 

We were happy to explore the political issues most talked about by the left and right wing political sides, as well as to see what happens if we were to combine the two. Our generated outputs relate to how people on Reddit feel regarding their respective political parties. It’s interesting to see what topics are most frequently talked about and what kinds of combinations we can expect to see in generated text from a particular party. This gives us insight into what a political party in general is thinking and helps to simulate a political party’s response to a new discussion on forthcoming topics.

We ran into ethical concerns when initially approaching our project because our original intention was to generate Reddit posts and comments and post these onto political discussion subreddits to get quantitative feedback. However, given the current state of the world with Coronavirus and protests, we decided to instead evaluate our results ourselves so as to not accidentally coerce people into action during these trying times.

In the future we would like to go back and try posting our generated texts to Reddit to quantify how popular they are in their respective political groups. It would also be beneficial to post them to a neutral political board and see what political party other people think the post belongs to. In improving our work, it’d be worthwhile to linearly interpolate political views together to see the differences in responses based on how much the model takes from one side versus the other. 


## Team Roles

Andy Do: Analysis on the Creighton, Carlisle, and Kuzco model for a given prompt. Worked on filling in the slides for the presentation.

Saieashwar Mukund: 

Chase Oden: Tested ideas and worked on general direction for project. Assembled powerpoint and the github README.md file. Formatted final video presentation. Analyzed final results in discussion section. 

Matthew Widjaja: 

Chris Wynne: 



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
 
Here is the link (you must unzip the file): https://drive.google.com/file/d/11U_56F8S0ZdDexSjvb8Vsgy4CU8Plb9S/view?usp=sharing

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

