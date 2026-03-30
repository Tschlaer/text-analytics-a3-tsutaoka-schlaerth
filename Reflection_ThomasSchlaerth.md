# Student A Reflection
## BSAN 6200: Text Mining & Social Media Analytics
## Assignment 3: Topic Modeling

## What I Learned

This assignment challenged me in parts of text mining and coding which I have not experienced yet. Working on unsupervised NLP led to continuous roadblocks as well as insightful outputs. After creating the code and trying to run it in Colab there were many issues with hangtime and code locking. I had to run the code on my own personal machine which was able to process the code without errors, however using the cloud in Colab led to difficulties. I had to go back and check what portions of the code i.e iterations, processes, and parameters, were not able to run in the cloud and change it. I also realized how much time topic modeling would take which slowed my overall work progress after every change to the code was implemented. It took me multiple hours to run the code over and over again, even after trying to change the runtime type. 

From the NMF modeling it was interesting to see how it compared to LDA modeling. I completed my coding portion after Josh completed his LDA modeling section. Comparing the two modeling types it was shocking to see how much better the NMF modeled compared to LDA. In multiple groups at differing k-scores the NMF model outputted a coherence score over 0.1 better than LDA. It was also surprising to see that the best coherence score was not uniform for each group. For some groups a lower k-value had the best coherence where in some other groups the inverse was true. I also was shocked to see that increasing the number of iterations by 100 or 200 led to a vastly improved coherence score. 

## Topic Interpretation

Interpreting the topics was a challenge for me because of the similarity of the top words per group. Many topics had character names or plot points as the most common words. This is understandable when it comes to movie reviews from various moviegoers but it was challenging to create topic names. It also was interesting to discover that many top words were actor names and their character names. Using these words I had to decide if I wanted to name the topics based on character names, movie names, actor names, or story points. 

For Group 1, many superhero topics were best described but naming the superhero or the movie. For example in Topic 9, the most common words were actors Tom Holland, Andrew Garfield, and Tobey Maguire. Because all these actors played Spiderman and were the main plot point from the movie No Way Home, it made the most sense to name this topic Spider-Men. In Group 2, the majority of the top words referenced the actors and directors from the movies leading to most of the topics being named with reference to the actors or directors. For example in Topic 1, the top words were comic, villain, nolan, and adaptation. With comics being the most significant word here, the topic name had to reference the director’s impact in relation to the comics which is why we called it Nolan’s Realism. Group 3, which had action/other movies, were dominated by marvel cinematic universe movies. It was a challenge to name the topics without just referencing the MCU. Because of this we had to find some workarounds like in topic 4. The top words from this topic were mainly characters from the Thor movies, but instead of naming this topic Thor characters, we decided to relate it to the plot of the movie which covers the Asgard Lore. 

Overall there were challenges in not being repetitive in each topic for the NMF modeling. I did use some of Josh’s topic names as inspiration. I also struggled in this section because I would not consider myself a creative person and I had many ‘writer’s blocks’ when trying to come up with names. 


## Challenges

My main challenge was processing time and code stalling. I had to work on multiple days to figure out which program would be able to run the code and in a timely manner. When it takes 30-40 mins to rerun the code after each change, it slows the workflow and makes it incredibly frustrating. I am also not proficient in coding and would not call myself a coder, so when I ran into issues and AI was not helpful it made it difficult to progress in the assignment. I was eventually able to get the code to work by asking a friend of mine who is a programmer on what issues may be caused by. He did not do any of the assignment for me, but did give me insight in trying my local machine for the code rather than Colab. He also spotted that my issue might be in the iterations, so I was able to take this information and ask AI to troubleshoot based on these insights. 

## Collaboration

Josh worked on the first portion of the code helping set up the document, cleaning the data, and setting up the EDA. He worked on the LDA modeling while I worked on the NMF modeling. We were able to discuss workload management because he was travelling the week the assignment was due. We discussed how to tackle the workload and how we can share responsibilities in code, Github creation, and assignment submission. 
