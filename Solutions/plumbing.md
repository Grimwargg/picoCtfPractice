plumbing 

Description
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to jupiter.challenges.picoctf.org 7480.

Solution

//connect to netcat 
//after connection it shows a lot of info so I have to pipe the output with a grep 'picoCTF'
grimwarg-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 
Not a flag either
...
Not a flag either
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
This is defintely not a flag
Not a flag either
Not a flag either
I don't think this is a flag either

//press Ctrl+C to cancel (stop connection to netcat)
//connect using the pipe with grep 
grimwarg-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep 'picoCTF'
picoCTF{digital_plumb3r_06e9d954}
^C
