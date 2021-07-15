# Microcorruption Binary Exploitation & Reverse Engineering Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47)

Challenge Page: [Cuscos](https://microcorruption.com/cpu/debugger)

## Walkthrough
- This challenge is similar to Hanoi challange we analyze `main` function where we get to know about `login` and from there it calls to other function `test_password_valid` & `unlock_door`.
- Now in the **Live Memory Dump** we can see **BDBDBDBDBDBDBDBD** been repeated same as in Hanoi. Also, we have to figure out what address we want to jump to.
- Now, when we observe `main` function we get to know that it is the `unlock_door` function which opens the door whose address is **0x4528** and that’s where we want to jump to. 
- Therefore, combining HEX of **BDBDBDBDBDBDBDBD** with the  **2845** in order for the little-endian machine to actually read it we get the password
## Password
`424442444244424442444244424442442845` in **HEX** form. 