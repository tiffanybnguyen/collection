#prints little things to make me happy bc im sad lol. i even slowed it down to make it readable. pov 3 AM coding
import sys
import time

arr = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]

text = input("Enter your message: ")
textA = list(text.split(" "))

perm = ""
temp = ""

def slowprint(s):
	for c in s + '\n':
		sys.stdout.write(c)
		sys.stdout.flush()
		time.sleep(1./250)

def Convert(string):
    list1=[]
    list1[:0] = string
    return list1

for word in textA:

  wordA = Convert(word)

  for i in range(len(wordA)):
    startIndex = 0
    endIndex = arr.index(wordA[i])
    
    while (startIndex != endIndex):
      slowprint(temp + arr[startIndex])
      startIndex = startIndex + 1
  
    perm = temp + arr[startIndex]
    temp = perm

  perm = perm + " "
  temp = perm
  slowprint(perm)
  time.sleep(1/10)

slowprint(perm + "<")
slowprint(perm + "<3")
