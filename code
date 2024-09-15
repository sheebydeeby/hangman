from getpass import getpass

def gap(x): #function to print a space
    for i in range(x):
        print("")
        

def valid_guess(): #only allows guesses that are valad
    while True:
        x = str(input("Guess: "))
        if not x.isalpha():
            print("Must only contain letters.")
            gap(1)
        elif len(x) >> 1:
            print("One letter at a time.")
            gap(1)
        elif x in used or x in answer:
            print("You've already guessed this.")
            gap(1)
        else:
            break
    return(x.lower())


def valid_password(prompt): #only allows words that are valid
    while True:
        x = str(getpass(prompt))
        if not x.isalpha():
            print("Must only contain letters.")
        else:
            break
    return(x.lower())

def hangman(x): #prints hangman based on how many lives are left
    gap(3)
    print(" =======                     Incorrect: " + (" ").join(used))
    if x >= 1:
        print(" [     O")
    else:
        print(" [")
    if x >=2: 
        if x == 2:
            print(" |     |")
            print(" |     |")
        elif x == 3:
            print(" |    /|")
            print(" |     |")
        elif x >= 4:
            print(" |    /|\\")
            print(" |     |")
    else:
        print(" |")
        print(" |")
    if x >= 5:
        if x == 5:
            print(" [    /")
        elif x == 6:
            print(" [    /\\")
    else:
        print(" [")
    print("_==_")
    gap(1)
    print(str((" ").join(answer)))
    gap(1)

#=========================[ END OF FUNCTION DEFS ]==================================

word = valid_password("What's the word?: ")
word_list = list(word)
global used
used = []
global answer
answer = []
lives_lost = 0


for i in range(len(word_list)): #creates blanks
    answer.append("_") 

hangman(0) #generates empty gallows


while answer != word_list: #repeats until guess is correct
    correct_guess = False
    guess = valid_guess()
    for i in range(len(word_list)): #converts all blank spaces where correct guess should be
        if word_list[i] == guess:
            answer[i] = guess
            correct_guess = True
            
    if not correct_guess:
        lives_lost = lives_lost + 1
        used.append(guess)
        
    hangman(lives_lost)
        
    if lives_lost == 6:
        print("Game over.")
        gap(1)
        print("The word was " + str(word) + ".")
        break
    
if lives_lost < 6:
    print("You win!")
    
    
