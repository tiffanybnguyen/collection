import random
from wordleList import wordsList
from wordleList import obscure

word = wordsList[random.randint(0, len(wordsList) - 1)]
wordL = list(word)
flag = True
counter = 0

tempGreen = []
tempYellow = []
tempGray = []
tempWordL = list(word)

row1 = "qwertyuiop"
row1 = list(row1)
row2 = "asdfghjkl"
row2 = list(row2)
row3 = "zxcvbnm"
row3 = list(row3)

row1C = []
row2C = []
row3C = []

dict = {
  "yellow" : "\u001b[38;5;220m",
  "green" : "\u001b[38;5;34m",
  "gray" : "\u001b[38;5;243m",
  "reset" : "\u001b[0m"
}

#check() checks for valid letters in the original word
def check(wordL):
  guessL = list(guess)
  
  #checks all letters for green
  for i in range(5):
    if guessL[i] == wordL[i]:
      tempGreen.append(i)

  #removes all green instances from guess
  for i in tempGreen:
    wordL.remove(guessL[i])

  #checks all remaining letters for yellow
  for i in range(5):
    if guessL[i] in wordL:
      tempYellow.append(i) 
      wordL.remove(guessL[i])

  #takes the remaining letters to make gray list
  for i in range(5):
    if i not in tempGreen and i not in tempYellow:
      tempGray.append(i)
    
#prints the guessed word in color
def printW():
  for i in range(5):
    if (i in tempGreen):
      print(dict.get("green") + guess[i] + dict.get("reset") + " ", end='')
    elif (i in tempYellow):
      print(dict.get("yellow") + guess[i] + dict.get("reset") + " ", end='')
    else:
      print(dict.get("gray") + guess[i] + dict.get("reset") + " ", end='')

  print()

#creates the default list for keyboard letters
def listCreate():
  
  for i in row1:
    row1C.append("reset")

  for i in row2:
    row2C.append("reset")

  for i in row3:
    row3C.append("reset")

#inserts the color decision for the alphabet keyboard array
def colorDecide():
  for i in tempGreen:
    if guess[i] in row1:
      temp = row1.index(guess[i])
      row1C[temp] = "green"
    elif guess[i] in row2:
      temp = row2.index(guess[i])
      row2C[temp] = "green"
    elif guess[i] in row3:
      temp = row3.index(guess[i])
      row3C[temp] = "green"

  for i in tempYellow:
    if guess[i] in row1 and not (row1C[row1.index(guess[i])] == "green"):
      temp = row1.index(guess[i])
      row1C[temp] = "yellow"
    elif guess[i] in row2 and not (row2C[row2.index(guess[i])] == "green"):
      temp = row2.index(guess[i])
      row2C[temp] = "yellow"
    elif guess[i] in row3 and not (row3C[row3.index(guess[i])] == "green"):
      temp = row3.index(guess[i])
      row3C[temp] = "yellow"

  for i in tempGray:
    if guess[i] in row1 and not (row1C[row1.index(guess[i])] == "green") and not (row1C[row1.index(guess[i])] == "yellow"):
      temp = row1.index(guess[i])
      row1C[temp] = "gray"
    elif guess[i] in row2 and not (row2C[row2.index(guess[i])] == "green") and not (row2C[row2.index(guess[i])] == "yellow"):
      temp = row2.index(guess[i])
      row2C[temp] = "gray"
    elif guess[i] in row3 and not (row3C[row3.index(guess[i])] == "green") and not (row3C[row3.index(guess[i])] == "yellow"):
      temp = row3.index(guess[i])
      row3C[temp] = "gray"
    
#prints list for keyboard letters with color
def printList():
  for i in range(len(row1)):
    if row1C[i] == "green":
      print(dict.get("green") + row1[i] + dict.get("reset") + " ", end='')
    elif row1C[i] == "yellow":
      print(dict.get("yellow") + row1[i] + dict.get("reset") + " ", end='')
    elif row1C[i] == "gray":
      print(dict.get("gray") + row1[i] + dict.get("reset") + " ", end='')
    else:
      print(row1[i] + " ", end='')
  print()
  
  for i in range(len(row2)):
    if row2C[i] == "green":
      print(dict.get("green") + row2[i] + dict.get("reset") + " ", end='')
    elif row2C[i] == "yellow":
      print(dict.get("yellow") + row2[i] + dict.get("reset") + " ", end='')
    elif row2C[i] == "gray":
      print(dict.get("gray") + row2[i] + dict.get("reset") + " ", end='')
    else:
      print(row2[i] + " ", end='')
  print()
  
  for i in range(len(row3)):
    if row3C[i] == "green":
      print(dict.get("green") + row3[i] + dict.get("reset") + " ", end='')
    elif row3C[i] == "yellow":
      print(dict.get("yellow") + row3[i] + dict.get("reset") + " ", end='')
    elif row3C[i] == "gray":
      print(dict.get("gray") + row3[i] + dict.get("reset") + " ", end='')
    else:
      print(row3[i] + " ", end='')
  print()


  
#main method (aka where it does the asking)

print("Instructions: guess the 5 letter word. Green means the letter is in the word and in the correct position, yellow means the letter is in the word, but \nnot in the correct position, and gray means the letter is not in the word.\n")
guess = input("Welcome to Qordle! Guess:  \n")
guessL = list(guess)

listCreate()

while (flag):

  if len(guess) != 5:
    print("invalid guess! only 5 characters.")
    guess = input("New Guess: ")
    guessL = list(guess)
    
  elif (guess in wordsList) == False and (guess in obscure) == False:
    print()
    print("Word not in list, try again.")
    guess = input("New Guess: ")
    guessL = list(guess)
    
  else:
    check(list(word)) #checks for correct letters
    print()
    printW() # prints word
    print()
    colorDecide() #changes color in keyboard list
    printList() #prints keyboard list
    print()
    
    tempGreen = []
    tempYellow = []
    tempGray = []
    counter = counter + 1
    
    if guess != word:
      guess = input("New Guess: ")
      guessL = list(str(guess))
    else:
      flag = False

if counter == 1:
  print ("congrats! you got the word in " + str(counter) + " try.")
else:
  print ("congrats! you got the word in " + str(counter) + " tries.")
