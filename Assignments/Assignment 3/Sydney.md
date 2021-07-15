# Microcorruption Binary Exploitation & Reverse Engineering Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47)

Challenge Page: [Sydney](https://microcorruption.com/cpu/debugger)

## Walkthrough
- After looking at the `main` function we get to know that first we run a `get_password` and then `check_password`.
- When we observe `check_password` carefully we will see 4 **cmp** which compares to values at an offset from the memory address at **r15**. These are the parts of the *password*.
- So now we will convert all these combined 4 **cmp** HEX to ASCII, but that doesn't work. So, by googling we get to know about something called *endianness of the CPU* which basically means it stores values in little endian format.
- So, by this when we convert our new HEX by this transform to ASCII we get `I.;h"nn&` which is the password.

## Password
`I.;h"nn&`