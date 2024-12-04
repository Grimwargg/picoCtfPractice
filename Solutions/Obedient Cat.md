Obedient Cat

Description
This file has a flag in plain sight (aka "in-the-clear"). Download flag(https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag).

Solution(in webshell)
//first we download the file using wget and the provided link
grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
--2024-12-04 06:59:18--  https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                                                100%[=================================================================================================================================================================>]      34  --.-KB/s    in 0s      

2024-12-04 06:59:18 (27.9 MB/s) - 'flag' saved [34/34]

//we verify that the file is downloaded in the current directory (pwd can be used to get full path)
grimwarg-picoctf@webshell:~$ ls
README.txt  convertme.py  file.txt  flag  warm

//we use "cat" or "less"  to get file contents 
grimwarg-picoctf@webshell:~$ cat flag 
picoCTF{s4n1ty_v3r1f13d_28e8376d}
