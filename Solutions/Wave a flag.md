Wave a flag

Description
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

Solution
//download the file
grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm
--2024-12-04 07:27:57--  https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                                                100%[=================================================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-12-04 07:27:57 (341 MB/s) - 'warm' saved [10936/10936]

grimwarg-picoctf@webshell:~$ ls           
README.txt  warm
//add execution rights for the file
grimwarg-picoctf@webshell:~$ chmod +x warm
grimwarg-picoctf@webshell:~$ ls
README.txt  warm
//execute file
grimwarg-picoctf@webshell:~$ ./warm 
Hello user! Pass me a -h to learn what I can do!
//execute file with arguments
grimwarg-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}
grimwarg-picoctf@webshell:~$ 