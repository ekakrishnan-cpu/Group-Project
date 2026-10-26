# Group-Project
print("Let's play hangman!")
import random 
wordbank = ['apple', 'banana', 'computer', 'python', 'coder'] 
answer = random.choice(wordbank) 
guess = input("Guess a letter") 
guessed_letters = []
attempts = 6 
while attempts > 0: 
  word = ""
  for letter in answer: 
    if letter in guessed_letters:
      word += letter + ""
  else: 
    word += ""
  if len(guess) > 1 or not guess.isalpha():
    print("Please enter a single valid letter.") 
    continue 
  if guess in guessed_letters:
    print("Already guessed.") 
    continue 
  if guess in answer:
    print("Good job! '{guess}' is in the word") 
  else: 
    print("Sorry, {guess} is not in the word") 
    attempts -= 1
if all(letter in guessed_letters for letter in answer): 
  print("Congrats! the word was '{answer}'!") 
else:
  print("Game over. The word was '{answer}'")
