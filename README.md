# Group-Project
import random 

while True: #instructions and general info
    print("Let's play hangman! But first, let's cover some rules.")
    print("A secret word has been chosen from our word bank.")
    print("You have 6 attempts to guess all the letters of that word.")
    print("Type one letter at a time and press Enter.")
    print("Wrong guesses reduce the attempts you have left.")
    
    wordbank = ['group', 'types', 'computer', 'python', 'coder'] 
    answer = random.choice(wordbank) #ensures that the word user has to guess is completely random from the word bank
    guessed_letters = []
    attempts = 6 
    
    while attempts > 0: #user guesses words when attempts are greater than 0
        word_display = ""
        for letter in answer:
            if letter in guessed_letters:
                word_display += letter + " "
            else:
                word_display += "_ "
        print("\nWord:", word_display)
        
        guess = input("Guess a letter: ").lower() 
        
        if len(guess) > 1 or not guess.isalpha(): #this is to show what to do when the user types more than one letter or types a word that is too long.
            print("Please enter a single valid letter. ") 
            continue 
            
        if guess in guessed_letters: #this is to check if the letter has already been guessed or not
            print("Already guessed. ") 
            continue 
            
        guessed_letters.append(guess) # adds letter to guessed letters list
      
        if guess in answer:  #user gets letter correct
            print(f"Good job! '{guess}' is in the word") 
        else: 
            print(f"Sorry, {guess} is not in the word")  #user is wrong
            attempts -= 1
            print("Lives left:", attempts)
            
        if all(letter in guessed_letters for letter in answer): #the user must enter all the correct letters in the word 
            print(f"Congrats! the word was '{answer}'!")
            break
    else: #this is what happens when attempts run out and the user persistently gets it wrong
        print(f"Game over. The word was '{answer}'")
        
    replay = input("Play again? Enter y/n: ").lower()   #checking if user wants to play again 
    if replay == 'y': #user says yes and the game loops with a new word
        continue
    else: #user says no and code stops running
        break
