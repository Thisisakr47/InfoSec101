# Microcorruption Binary Exploitation & Reverse Engineering Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47)

Challenge Page: [Hanoi](https://microcorruption.com/cpu/debugger)

## Walkthrough
- After looking at the `main` function we get to know that we only run `login`.
- Now we observe `login` from which we get to know about two function `test_password_valid` & `unlock_door`
- From `test_password_valid` we get to know that in order to pass this level our password should be something that after calling `test_password_valid` places into **r15** zero. Also we must get the value **0x65** to be into memory address **0x2410**.
- Now we can see that unlocking the level depends upon **0x65** value being & not at **0x2410** memory address. 
- so now we to input **4444444444444444** from the **Live Memory Dump** followed by **65** which will be our password.

## Password
`444444444444444465` in **HEX** form.