Python Wrangling

Description
Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?

Solution
//download the files ("this Python script"=ende.py, "this password"=pw.txt, "the flag"=flag.txt.en)
grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py
--2024-12-09 12:21:34--  https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: 'ende.py'

ende.py                                                             100%[=================================================================================================================================================================>]   1.30K  --.-KB/s    in 0s      

2024-12-09 12:21:34 (382 MB/s) - 'ende.py' saved [1328/1328]

grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/pw.txt
--2024-12-09 12:21:46--  https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/pw.txt
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'pw.txt'

pw.txt                                                              100%[=================================================================================================================================================================>]      33  --.-KB/s    in 0s      

2024-12-09 12:21:46 (14.5 MB/s) - 'pw.txt' saved [33/33]

grimwarg-picoctf@webshell:~$ ls
README.txt  ende.py  pw.txt
grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/flag.txt.en
--2024-12-09 12:22:15--  https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/flag.txt.en
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: 'flag.txt.en'

flag.txt.en                                                         100%[=================================================================================================================================================================>]     140  --.-KB/s    in 0s      

2024-12-09 12:22:15 (52.6 MB/s) - 'flag.txt.en' saved [140/140]

grimwarg-picoctf@webshell:~$ ls
README.txt  ende.py  flag.txt.en  pw.txt

//run ende.py
grimwarg-picoctf@webshell:~$ python3 ende.py 

//it prompts that it needs arguments to encode/decode a file, so I will pass to it the decoding file 
Usage: ende.py (-e/-d) [file]

//I check also pw.txt to see the password
grimwarg-picoctf@webshell:~$ less pw.txt     
grimwarg-picoctf@webshell:~$ 

//I run ende.py with arguments and I give it the expected passwords
grimwarg-picoctf@webshell:~$ python3 ende.py -d flag.txt.en
Please enter the password:6008014f6008014f6008014f6008014f
picoCTF{4p0110_1n_7h3_h0us3_6008014f}
grimwarg-picoctf@webshell:~$ 
