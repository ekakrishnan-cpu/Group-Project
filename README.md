# Group-Project
import random 
while True: 
  print("Let's play hangman! But first, let's cover some rules.")
  print("A secret word has been chosen from our word bank.")
  print("You have 6 attempts to guess all the letters of that word.")
  print("Type one letter at a time and press Enter.")
  print("Wrong guesses reduce the attempts you have left.")
  wordbank = ['group', 'types', 'computer', 'python', 'coder'] 
  answer = random.choice(wordbank) 
  guessed_letters = []
  attempts = 6 
  while attempts > 0: 
    guess = input("Guess a letter: ").lower() 
    word = ""
    for letter in answer: 
      if letter in guessed_letters:
        word += letter + ""
      else: 
        word += "_ "
    if len(guess) > 1 or not guess.isalpha():
      print("Please enter a single valid letter. ") 
      continue 
    if guess in guessed_letters:
      print("Already guessed. ") 
      continue 
    guessed_letters.append(guess) 
  
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
  replay = input("Play again? Enter y/n: ").lower() 
  if replay == 'y':
    continue
  else: 
    break 
