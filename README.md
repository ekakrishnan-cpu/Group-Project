# Group-Project
print("Let's play hangman!")
import random 
wordbank = ['apple', 'banana', 'computer', 'python', 'coder'] 
answer = random.choice(wordbank) 

guess = input("Guess a letter:")
guessed_letters = []
