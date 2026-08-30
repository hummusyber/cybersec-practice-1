# cryptohack
basic cryptography...

## Intro
1. Challenge involved going through a list of various ASCII values using a for loop, then printing corresponding ASCII characters to obtain a flag.
'''python
l=[99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110, 116, 52, 98, 108, 51, 125]
for i in range(0,len(l)):
    print(chr(l[i]))
'''
