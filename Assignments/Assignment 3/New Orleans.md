# Microcorruption Binary Exploitation & Reverse Engineering Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47)

Challenge Page: [New Orleans](https://microcorruption.com/cpu/debugger)

## Walkthrough
- After looking at the `main` function we get to know that first we run a `create_password` then `get_password` and then `check_password`. 
- By Observing `create_password` we get to know that it moves some bytes using **mov.b** at incrementing offsets relative to **0x2400**.
- Also the final **mov.b** instruction at **0x44ac** moves a null byte into the last memory location before returning the method call.
- Now by observing `check_password`we get to know that 8 **cmp.b** operations are performed from the same offset we have had when `create_password` started writing those bytes. Therefore, we can conclude that `create_password` writes the password to memory and the `check_password` just compares those bytes to the ones entered by the user.
- Now we set a *breakpoint* just after `create_password` is done at **0x4440** with **break 4440**. We will set a next *breakpoint* at the `check_password` at **0x44c2** where character comparisons happens.
- At the first breakpoint we can see that the bytes 6f3f 3973 727a 7700 were written from 0x2400 onwards, which on converting to ASCII gives `o?9srzw` which was the passsword.

## Password
`o?9srzw`