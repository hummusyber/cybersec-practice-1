# cryptohack
basic cryptography...

## Intro
1. Challenge involved going through a list of various ASCII values using a for loop, then printing corresponding ASCII characters to obtain a flag (using chr() function).
```python
l=[99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110, 116, 52, 98, 108, 51, 125]
for i in range(0,len(l)):
    print(chr(l[i]))
```

2. Decoded an encoded hex string into bytes using bytes.fromhex() function.
```python
print(bytes.fromhex('63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d'))
```

3. Decoded a hex string, then encoded the same into base64 to receive the flag.
```python
import base64
decoded=(bytes.fromhex('72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf'))
encoded=(base64.b64encode(decoded))
print(encoded)
```
