# Bandit Level 12 to 13 Writeup


Author: [Ayush Kumar](https://github.com/Thisisakr47) 

Problem Page: [bandit12](https://overthewire.org/wargames/bandit/bandit13) 

## List of Commands Used
```
ls    - list files in a directory
mkdir - creates new directory
cp    - copy files and directories 
cd    - to change the current working directory
cat   - prints the contents of a file
mv    - to rename and move files & directories
file  - outputs the type of file
xxd   - creates a hexdump or do the reverse
gzip  - compresses single file and creates a compressed file
bzip2 - same as gzip, creates smaller archives but has a slower decompression time and higher memory use 
tar   - compress a group of files into an archive

```

## Walkthrough
- Use `ls` command to see all the files(i.e data.txt) in the current directory
- Create a new directory under /tmp using `mkdir` command 
- Now Copy the file **data.txt** to the new directory you just created using `cp` command
- Reverse the hexdump (i.e data.txt) into a new file using `xxd -r` command
- Check the file type of the new file created using `file` command
- Change the extension of the new file to **.gz** using mv & decompress the file using `gzip -d` command
- Check the file type and then change its extension to **.bz2** & decompress using `bzip2 -d` command
- Check the file type and then change its extension to **.gz** & decompress using `gzip -d` command
- Check the file type and then change its extension to **.tar** & extract using `tar xf` command
- Check the file type of **data5.bin** and then change its extension to **.tar** & extract using `tar xf` command
- Check the file type of **data6.bin** and then change its extension to **.bz2** & decompress using `bzip2 -d` command
- Check the file type of above file and then change its extension to **.tar** & extract using `tar xf` command
- Check the file type of **data8.bin** and then change its extension to **.gz** & decompress using `gzip -d` command
- Now use `cat` command to see the contents(i.e password) of final decompressed file

## Password
`8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

## Bash/Python script to automate the process
```
sshpass -p '5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu' ssh bandit12@bandit.labs.overthewire.org -p 2220 'bash -s' < bandit12.sh 

bandit12.sh contains :-

echo $(mkdir /tmp/akr)
echo $(cp data.txt /tmp/akr)
echo $(cd /tmp/akr)
echo $(xxd -r data.txt > 1)
echo $(mv 1 1.gz)
echo $(gzip -d 1.gz)
echo $(mv 1 1.bz2)
echo $(bzip2 -d 1.bz2)
echo $(mv 1 1.gz)
echo $(gzip -d 1.gz)
echo $(mv 1 1.tar)
echo $(tar xf 1.tar)
echo $(mv data5.bin 1.tar)
echo $(tar xf 1.tar)
echo $(mv data6.bin 1.bz2)
echo $(bzip2 -d 1.bz2)
echo $(mv 1 1.tar)
echo $(tar xf 1.tar)
echo $(mv data8.bin 1.gz)
echo $(gzip -d 1.gz)
echo $(cat 1)

```
