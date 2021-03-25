# Capstone2

    • Classifying different types of music 
        ◦ What if I looked at the image of the frequencies and tried to see if there were parallels? 
        ◦ What key its in? Blues vs jazz? 
        ◦ Data: https://www.kaggle.com/c/mlp2016-7-msd-genre
        ◦ Similar project https://www.kaggle.com/andradaolteanu/gtzan-dataset-music-genre-classification
    • Changing the word prediction audio-to-text in a presentation
        ◦ So here is the problem- when I watched class lecture recordings, the Zoom recordings would provide audio transcripts and closed captioning for the meetings.  They did a great job for the most part. 
        ◦ They did poorly in one respect – with specific presentations given by professors, the AI totally didn’t know what to do with weird words like sinusoidal, or odd vocab words that aren’t common… its more likely that the words are “sinus oil” instead of sinusoidal…
        ◦ But, if they looked on the screen, the professor has the word “sinusoidal” on the screen. 
        ◦ If we used computer vision to look on the screen, we could easily see that sinusoidal is a word that’s more likely to be said than “sinus oil”
        ◦ In a Bayesian context, you could update the probability of the word being “sinusoidal” because the word “sinusoidal” is on the screen
        ◦ For my project, could I do computer vision to look at the words on a screen and create a list of words on the screen (or ever on the screen during the presentation)
        ◦ From this list, I could show the math of how you could update the probability for the text generator.  I dont know if I could actually build something that predicts the t
    • Clustering Instagram followers for Analysis
        ◦ I would need to web scrape my followers using selenium, not crazy crazy hard 
        ◦ I would need to see who my folllowers followers are too, and I would map all of these people out 
        ◦ I would run unsupervised learning(?) clustering to see what clusters of friends I had where given the mutual connections… the columns would be whether somebody is connected to that other person or not
        ◦ You could see how many people’s followers are spam or not too… how many spam followers do I have? Are they just not connected to anybody that I know? How many friends like that can I have? 
