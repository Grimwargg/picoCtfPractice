convertme.py

Description
Run the Python script and convert the given number from decimal to binary to get the flag.

Solution
//download the file
grimwarg-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2024-12-04 07:40:50--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                                        100%[=================================================================================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-12-04 07:40:51 (551 MB/s) - 'convertme.py' saved [1189/1189]

//run the file using python3
grimwarg-picoctf@webshell:~$ python3 convertme.py 
If 75 is in decimal base, what is it in binary base?
Answer:1001011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
grimwarg-picoctf@webshell:~$ 