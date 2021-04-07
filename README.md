# A Transcription Prescription...

## The Problem: [Otter.AI](http://otter.AI)'s Sub-Par Performance

In my classes, pre-recorded Zoom lectures would use [Otter.ai](http://otter.ai) to transcribe the audio of a presentation.  Many of these audio-to-text translations missed the mark where they could have found the answer.  

> The audio was analyzed in a vacuum, without reading the words on the screen to give any idea of what the unique vocab words could be.

For example, word like Euler were said and interpreted as "oil or". If it were a normal conversation happening, that would be an intelligent transcription.  But, this was a math lecture. Also, the word Euler was written on the screen! If you used computer vision to make a list of all the vocabulary words on the screen, you could predict what the word was with much better accuracy. 

### Example: An Artificial Lack of Intelligence

This is a screenshot from a lecture from one of my courses on lean manufacturing.  The professor says the words "MRP", an acronym for Material Resource Planning.  [Otter.AI](http://otter.AI) interpreted this as "msrp" at first and then latter "Mr P", where the professor made no mention of a "Mister P".  But, if the AI was intelligent enough to look at the screen, it would see the word MRP written several times. Wouldn't you think that "MRP" was what she was talking about given that the letters "MRP" are on the screen on **five different occasions**?

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled.png)

## The Bayesian Solution:

The odds of the average spoken word being Euler is much lower than the odds of it beings the phrase "oil or". Yet, given the fact that the word appears on the screen, this probability would be much higher.   

### How do Speech Recognition ML Algorithms Work?

When a word is heard, the algorithm assigns it a probability of being a certain word.  Where somebody may say the word "crew", it may assign a 90% probability of it being this word, and it may give it a 10% chance of it being "brew".  The algorithm predicts that it's the word said with the highest probability. 

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/CodeCogsEqn_(2).gif](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/CodeCogsEqn_(2).gif)

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/CodeCogsEqn_(5).gif](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/CodeCogsEqn_(5).gif)

### Scope of This Capstone - Dumbing it Down

While the original idea for my capstone project would be to create a minimum viable product for a piece of software that would do just this, my instructors advised me that with one week of time, I may not accomplish this and that if I focused on building a neural network that predicted text given images from the ground up, I would learn more about neural networks and I would appreciate the complexity of pre-trained algorithms, like Tesseract which do a *phenomenal* job of reading text off of a screen.  

## My Capstone: A Neural Network Text Image Classifier

For my capstone project, I chose to train a neural network to classify images of words that I generated. The intention of this was to more thoroughly understand how I could create a neural network from scratch, and have and idea of the complexity and computing power that must go in to training more robust neural networks that can easily predict text from an image.  

### My Neural Network: The Little Model That Could

Under the guidance of my bootcamp instructors, I created a simple model by generating images of words and training a neural network to learn what these words were.  I iterated through a few types of models, playing with parameters and how I varied my images so that my model could properly train on them.   

> If you don't mind me rambling about how I tinkered with my model, read what I have written below. If that's boring, just skip down to the bottom (🔎**Tesseract**) where I show you how the pre-trained Tesseract model performs a million times better than my baby model.

 

# Lions, Tigers, and Bears (Oh My)

I trained my model to learn how to recognize the three words "lions", "tigers", and "bears". I created images of these words using matplotlib. I used this to change the font size, the position of the word on the screen, and that rotational skew of the word. I build a custom data image generator that randomly selected one of these words, applied a series of transformations to the word which differentiated it from other words, and ran a model on it to see if it could learn to predict which word I was talking about.  

### First Try: Changing Size and Position

The model was trained on images of the word "lions", "tigers", and "bears", thrown about in random (x,y) coordinates on the image, also greatly varying in size.  This model, trained on 1,000 randomly generated parameters, performed horribly.  No better than random guessing.  Was my model not working? I wondered.  

### Was My Model Even Working?

I changed the model to just randomly generate images of set of words, but making the images at size that were mildly variable.  I randomly picked the font size to be between 30 and 50 and it seemed to do the trick. My model quickly learned the patterns of the words and was able to predict which word it was with a 100% accuracy. Cool to see how random pixels can be recognized as words. Smart model... I wonder how far I could take it on my computer. 

### Trying to Break It

Now that I knew that my model worked... how far could I take it on my local machine without it breaking? I knew that my original model would work if I generated enough images and gave it enough time and computing power. I tried this! .... but my computer crashed ... twice.  

So, I tried to have it learn to train by giving it different parameters to train over.  I tried training it on words that were the same size, but varied in their x and y positions. This had a hard time training, but when I trained it on words that just changed in x position, it was able to learn this perfectly. 

> I knew that with enough computing power, it would be able to figure this out.

### How Smart Could I Make My Model?

I tried to confuse my model in a variety of ways to see what it could pick up.  Rotating the images? ✅  Drastically changing the size of my images? ✅  Replacing random characters in the words with the letter "a"? ✅  Replacing two letters in the word with the letter "a"? ✅  Replacing two letters in the word with a random letter? 🚫 It didn't learn well on the last one. Yet, I know that with enough computing power and enough images of these words, I am sure that it could understand this.  

## What was the computer learning?

When modifying the size of the word, I could understand how the computer found a pattern in it's layers.  When changing the position of the word on the screen, the computer eventually learned that position was irrelevant, and focused on the shape of the black pixels, ignoring where these pixels were on the screen. What about with rotations? I guess that it picked up a pattern in a radial dimension. Really interesting how it figured all of this out. 

### Implications of My Baby Model?

As my first real personal project building a neural network from scratch, it blows me away by what a computer can pick up so quickly. The most profound part of this is that today we have free models like Tesseract which outperform my model significantly.  People are rolling out powerful open source pre-trained models which push forward the landscape of artificial intelligence. Combine that with the notorious Moore's law, and the future is going to be a hell of a ride.  

# More Power: Brute Force in Google Colab

I paid $10 for Google Colab Pro, an environment where I could run my model without it crashing my  computer.  This surprised me with how well it performed compared to my computer's sub-par performance. So, I started playing with the combinations of models that my computer was unable to run.   

### Model Iterations

1. First, I tried to confuse the model as much as possible to see if it could learn the combinations of parameters I gave it.  I replaced two letters in each word with random characters, I changed the rotation by 60 degrees, I changed the size dramatically, and I shifted the x and y position of the word.  I generated 10,000 images and ran this for 20 epochs. It had an accuracy of 0.42 and a loss of 6.2. This was terrible. Obviously, this was over-fitting.  So, I changed my dropout from 0.1 to 0.3 and I tried again.
2. With the dropout level of 0.3, I improved accuracy to 0.43 and loss to 3.3, but this was not as great as I wished.  So, I decided to decrease the learning rate to see if this would help.  
3. This did not help...

### What Could I Train On?

On Google Colab, I trained on models that had failed on my local machine.  I was successful in training on models that changed multiple letters within the words to random characters, and changing the size of the words randomly. 

### Final Model

I for my final model, I classified images of the words "lions", "tigers" and "bears", adjusted in their position on the screen, their rotation, size, and I randomly replaced two letters inside of the words with the letter "a". This model had an accuracy of 0.60 and a loss of 3.4.

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%201.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%201.png)

Version 1

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%202.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%202.png)

Version 2

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%203.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%203.png)

Version 3 

## Tesseract: Why My Model Should Be Self Conscious

The [Tesseract optical character recognition software](https://en.wikipedia.org/wiki/Tesseract_(software)) is so competent that my model should feel bad about itself. With three lines of code, I imported everything I needed and found all of the text on a screenshot from a PowerPoint slide.  If and when I make a better audio transcriber, I would want to use a software like Tesseract to read all of the words on the screen.  

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/screenshot.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/screenshot.png)

PowerPoint slide image read with Tesseract

![A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%204.png](A%20Transcription%20Prescription%20c9ad75d60ccb41819e33300966e19aa8/Untitled%204.png)

Using Tesseract to read the image of the PowerPoint presentation 

### Pre-Trained Models or Training Our Own Models?

If I were to build a better audio transcriber, I would use a pre-trained model before anything that I would make myself.   "If I have seen further than others, it is by standing upon the shoulders of giants" -Isaac Newton.  But, with something bespoke, you can be much more specific in tailoring the needs of the model to the problem at hand.  

# Future Extensions of this Project

I would love to integrate an OCR like Tesseract into my software and find a way to change the underpinnings of a speech recognition software to build a better audio transcriber.