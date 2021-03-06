# Password 1

We uncovered the first password encryption file. Can you crack it for us?

# Solution

The challenge was given a password1.py file. Open the file I could see

```python
import random

def checkPassword(password):
    if(len(password) != 43):
      return False
    if(password[26] == 'r' and
      password[33] == 't' and
      password[32] == '3' and
      password[16] == '3' and
      password[4] == 'F' and
      password[21] == 'r' and
      password[38] == '1' and
      password[18] == 'c' and
      password[22] == '@' and
      password[31] == 'g' and
      password[7] == 'u' and
      password[0] == 'C' and
      password[6] == 'p' and
      password[39] == '3' and
      password[3] == 'T' and
      password[25] == '3' and
      password[29] == 't' and
      password[42] == '}' and
      password[12] == 'g' and
      password[23] == 'c' and
      password[30] == '0' and
      password[40] == '3' and
      password[28] == '_' and
      password[20] == '@' and
      password[27] == '$' and
      password[17] == '_' and
      password[35] == '3' and
      password[8] == '7' and
      password[24] == 't' and
      password[41] == '7' and
      password[13] == '_' and
      password[5] == '{' and
      password[2] == 'C' and
      password[11] == 'n' and
      password[9] == '7' and
      password[15] == 'h' and
      password[34] == 'h' and
      password[1] == 'Y' and
      password[10] == '1' and
      password[37] == '_' and
      password[14] == 't' and
      password[36] == 'r' and
      password[19] == 'h'):
      return True
    return False

password = input("Enter password: ")
if(checkPassword(password)):
  print("PASSWORD ACCEPTED\n")
else:
  print("PASSWORD DENIED\n")
```

Looking at the source code, I could see that the flag was splited to separate characters, thus I have to sort all of that char to get the flag.

```python
password = ['']*43
password[26] = 'r'
password[33] = 't'
password[32] = '3'
password[16] = '3'
password[4] = 'F'
password[21] = 'r'
password[38] = '1'
password[18] = 'c'
password[22] = '@'
password[31] = 'g'
password[7] = 'u'
password[0] = 'C'
password[6] = 'p'
password[39] = '3'
password[3] = 'T'
password[25] = '3'
password[29] = 't'
password[42] = '}'
password[12] = 'g'
password[23] = 'c'
password[30] = '0'
password[40] = '3'
password[28] = '_'
password[20] = '@'
password[27] = '$'
password[17] = '_'
password[35] = '3'
password[8] = '7'
password[24] = 't'
password[41] = '7'
password[13] = '_'
password[5] = '{'
password[2] = 'C'
password[11] = 'n'
password[9] = '7'
password[15] = 'h'
password[34] = 'h'
password[1] = 'Y'
password[10] = '1'
password[37] = '_'
password[14] = 't'
password[36] = 'r'
password[19] = 'h'
print(password)
for char in password:
    print(char, end="")
```

# Flag

`CYCTF{pu771ng_th3_ch@r@ct3r$_t0g3th3r_1337}`
