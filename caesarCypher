#encodes user input into chosen displacement according to the Caesar Cypher

oString = str(input("Enter sentence: "))
diff = int(input("Enter difference: "))

oAlpha = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]

aAlpha = ["", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", ""]
i = 26 - diff

# initializes the modified alphabet
x = 0
while x < 26 :
  
  if (diff + i > 25) :
    i = i - 26
  
  aAlpha[i] = oAlpha[x]

  i += 1
  x += 1

t = 0
c = ""

while t < len(oString) :
  if (oString[t] == " ") :
    c += " "
    t += 1
  else :
    c += (aAlpha[oAlpha.index(oString[t])])
    t += 1

print("Your Caesar Cypher: " + c)
