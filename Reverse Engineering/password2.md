# Password 2

You did so well on the last one, can you try this?

# Solution

Looking at the source code, I could see that checkPassword funtion is required an arguments password with length is 47. Look through the source I've seen a line `return password` with the password was made mess. I've tried to put it in the input then I got the flag

```python
import random


def checkPassword(password):
    if(len(password) != 47):
        return False
    newPass = list(password)
    for i in range(0, 9):
        newPass[i] = password[i]
    for i in range(9, 24):
        newPass[i] = password[32-i]
    for i in range(24, 47, 2):
        newPass[i] = password[70-i]
    for i in range(45, 25, -2):
        newPass[i] = password[i]
    password = "".join(newPass)

    print(password)
    # return password == "CYCTF{ju$@rcs_3l771l_@_t}bd3cfdr0y_u0t__03_0l3m"


password = input("Enter password: ")
if(checkPassword(password)):
    print("PASSWORD ACCEPTED\n")
else:
    print("PASSWORD DENIED\n")

```

# Flag

`CYCTF{ju$t_@_l177l3_scr@mbl3_f0r_y0u_t0_d3c0d3}`
