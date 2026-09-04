<H3>NAME: VAISHNAVI T</H3>
<H3>REGISTER NO: 212225100057</H3>
<H3>EX. NO.8</H3>
<H1 ALIGN =CENTER>Implementation of Semantic Analysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.

## Program:

Insert your code here
```
import nltk
from nltk.corpus import wordnet

# Downloads
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')

sentence = input("Enter a sentence: ")

# Simple tokenization
words = sentence.split()

# POS tagging
pos_tags = nltk.pos_tag(words)

synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())

            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

print("POS Tags:", pos_tags)
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```

## Output

<img width="1067" height="243" alt="image" src="https://github.com/user-attachments/assets/fa93e8c4-d344-42ad-ac94-303a7badaadf" />

## Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
