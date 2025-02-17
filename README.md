# One_alpha_Quiz
Python Code for:- Guessing a word, one letter (A-Z) at a time until you get a word match. Word list can be added.
import random
# creating a word list from which user will guess the word, one letter at a time
word_list=["beautiful","handsome","loyal"]

# randomely select word from word list for user to guess the word
rand_choice= random.choice(word_list)
word_length=len(rand_choice)
placement =" "
# replaces random word position with "-" which user will have to quess appropriate letters
for position in range(word_length):
    placement += "_"
print(placement)
# informs user of how many letters are in the word
print(f"The word is a/an {word_length} letter word")
correct_answer= []
condition = False
# informs user the chances available for guessing the correct letters
chances=(word_length) + 1
# while loop for user input and info on chances left for user
while not condition:
    Guess=input(" Please guess a letter in the word : \n").lower()
    display= " "
    chances-=1
    if chances>=0:
            print(f"you now have {chances} chances to guess the word")
  # "for loop" to check if user letter guess matches a letter in the word,and insert guessed letter at appropriate posittion
            for letter in rand_choice:
                    if letter == Guess:
                        display += Guess
                        correct_answer.append(Guess)
                    elif letter in correct_answer:
                        display += letter
            # print(letter.replace(letter,Guess))
                    else:
                        display += "_"
             
            print(display)
  # informs if chances for user to guess have been exhausted
    else:
        print(f"You have exausted All your Chances, GAME OVER")
        condition=True
        continue
    
  # checks if all user guesses have been done correctly to inform user if game is won.
    if "_" not in display:
        condition = True
        print("Congratulations, you win")
