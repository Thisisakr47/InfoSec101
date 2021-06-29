# PicoGym Web Exploitation Writeup

Author: [Ayush Kumar](https://github.com/Thisisakr47)

Challenge Page: [Scavenger Hunt](http://mercury.picoctf.net:21939/)

## Walkthrough
- At first I inspected the page to see the contents of HTML/CSS/JavaScript. The **HTML** and **CSS** contained the two part of the picoCTF Flag.
- In its **JavaScript** file it gave hints that the other parts of the flag are contained in various files in the webpages like robots.txt etc.
- Now we can either list all the files in a website using **Brute Force** or can simply follow the hints, here I choosed the later one.
- The 1st hint was pretty simple and just basic googling revealed that we have to look into **robots.txt** file.
- Now inside index.txt we get another hint indicating some file related to **Apache Server** which from further googling I got to know that .htaccess manages Apache Server permission which futher revealed that we have to look for a file named **.htaccess**.
- Inside this we get another hint indicating we have to look for one more file. This one was tough but I searched on google regarding this very intensively and got hint that it could be a file named **.DS_Store** and bingo it worked out and the picoCTF challenge was completed.

## Flag
`picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}`

## Useful resources (if any)
 
Always **[Google](https://www.google.com/)** stuffs you don't understand.
