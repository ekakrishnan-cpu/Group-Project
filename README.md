# Group-Project
print("Let's play hangman!")
import random 
wordbank = ['apple', 'banana', 'computer', 'python', 'coder'] 
answer = random.choice(wordbank) 
guessed_letters = []
wrong_guesses = 0
