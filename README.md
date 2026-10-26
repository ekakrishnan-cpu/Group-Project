# Group-Project
print("Let's play hangman!")
import random 
wordbank = ['apple', 'banana', 'computer', 'python', 'coder'] 
answer = random.choice(wordbank) 
guessed_letters = []
attempts = 6 
while attempts > 0: 
  guess = input("Guess a letter").lower() 
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
    print(f"Good job! '{guess}' is in the word") 
  else: 
    print(f"Sorry, {guess} is not in the word") 
    attempts -= 1
  if all(letter in guessed_letters for letter in answer): 
    print(f"Congrats! the word was '{answer}'!")
    break
else:
  print(f"Game over. The word was '{answer}'")
