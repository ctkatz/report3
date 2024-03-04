# Homework 3 Report

## Basics
External resources used on this assignment:
* 

Classmates you talked to about this assignment:
* 

How many hours did you spend on this assignment?
* 

### Group Member #1 Carly Mcadam
* Your middlebury email: cmcadam@middlebury.edu
* How many hours did you spend on outside of class on CS 457 this week, _excluding this assignment_? 
3
### Group Member #2 Chloe Katz
_Delete this section if you worked alone_
* Your middlebury email: ctkatz@middlebury.edu
* How many hours did you spend on outside of class on CS 457 this week, _excluding this assignment_? 
3
## Report

### Accuracy
What is the tag-level accuracy of your system?

We have an 89.7% tag level accuracy.

### Method
How did you handle unknown words in your system?

If the word is in the emmision log probabilites, we run the code normally.
When the word matches to the unknown token, we operate differently.
If not, we do the tag and the probability our unknown word is a certain tag in place of the emission log probabilites, still adding the transition probabilities normally because that is only based on the tag. 

### Error Analysis
Identify three errors in the automatically tagged data, and analyse them (i.e., for each error,
write one brief sentence describing the possible reason for the error and how it could be
fixed). To identify errors, you can use the `error_helper.py` script that is provided in the starter code.
* Error 1
  * Tokens: "Try different things out and see what feels right, what sounds best." we are getting an error with the word right.
  * Actual tags: adjective
  * Predicted tags: adverb
  * Analysis: Normally, following the word feels an adverb is very common, example: I feel strongly, I feel jumpy, etc. Right can also be mapped to a lot of different tags, so it can be an adjective or a noun most commonly, but it's not suprising that the tag of the word was misintrpreted to adjectives neighbor, adverb.
* Error 2
  * Tokens: "And even my cuffs and everything 's on my bed." : we are getting an error with the word cuffs
  * Actual tags: noun
  * Predicted tags: punctuation
  * Analysis: commonly, conjuctions like and have punctuation before them, and the word my is often followed by punctuation as well. We think with the sentence structure of this token, it's unsuprusing that it misintepreted a word (probably an unkown word, at that), like cuffs.
* Error 3
  * Tokens: The city suffered minor damage during WWII , and suffered extensive urban planning in the decades that followed , as the nation rapidly industrialized and urbanized . Issue with WWII
  * Actual tags: Proper noun
  * Predicted tags: number
  * Analysis: WWII: an unknown word, which makes the probability  determined by the words around it. The word during often refers to a certain time or date, which means that it's often followed by a number, so it's unsuprising that we get a number here instead of the correct designatiion, a proper noun.
