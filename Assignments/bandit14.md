# Bandit Level 14 to 15 Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47) 

Problem Page: [bandit14](https://overthewire.org/wargames/bandit/bandit15) 

## List of Commands Used
```
nc -  reads and writes data across network connections, using TCP or UDP protocol

```

## Walkthrough
- use `nc` command to connect to port 30000 on localhost
- Type the password of previous level (i.e 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e) to get the password for next level

## Password
`BfMYroe26WYalil77FoDi9qh59eK5xNr`

## Bash/Python script to automate the process
```
sshpass -p '4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e' ssh bandit14@bandit.labs.overthewire.org -p 2220 'bash -s' < bandit14.sh </br>
**bandit14.sh contains**</br>
echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000

```
