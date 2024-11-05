### NAME : Suji G
### REGISTER NO : 212222230152
### DATE: 27.10.24

## EX. NO.6         Implementation of Semantic Analysis

### Aim: 
To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.

### Algorithm:
Step 1: Import the nltk library.</br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.</br>
Step 3:Accept user input for the text.</br>
Step 4:Tokenize the input text into words using the word_tokenize function.</br>
Step 5:Iterate through each word in the tokenized text.</br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.</br>
•	Print each word along with its corresponding part-of-speech tag.</br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).</br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.</br>
•	Print the unique sets of synonyms and antonyms.</br>

### Program :
```
# Import necessary libraries
import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

# Download necessary NLTK data
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')

# Input sentence
sentence = input("Enter a sentence: ")

# Tokenize the sentence into words
words = word_tokenize(sentence)

# Identify the parts of speech for each word
pos_tags = nltk.pos_tag(words)

# Print the parts of speech
print("Parts of Speech Tags:")
for word, tag in pos_tags:
    print(f"{word}: {tag}")

# Identify synonyms and antonyms for each word
synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())
            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

# Print the synonyms and antonyms
print("\nSynonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```
## Output :
![{2203F69B-97AD-4FE4-8FA1-72573D22462A}](https://github.com/user-attachments/assets/a12b9ece-ccf5-486c-a50b-a93793b52591)

## Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
