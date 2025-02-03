Bases


Description
What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

Solution
//solution 1 (chat GPT)
grimwarg-picoctf@webshell:~$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
l3arn_th3_r0p35
grimwarg-picoctf@webshell:~$ 

//solution 2, read help of base 64 convertor
grimwarg-picoctf@webshell:~$ base64 --help
Usage: base64 [OPTION]... [FILE]
Base64 encode or decode FILE, or standard input, to standard output.

With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -d, --decode          decode data
  -i, --ignore-garbage  when decoding, ignore non-alphabet characters
  -w, --wrap=COLS       wrap encoded lines after COLS character (default 76).
                          Use 0 to disable line wrapping

      --help     display this help and exit
      --version  output version information and exit

The data are encoded as described for the base64 alphabet in RFC 4648.
When decoding, the input may contain newlines in addition to the bytes of
the formal base64 alphabet.  Use --ignore-garbage to attempt to recover
from any other non-alphabet bytes in the encoded stream.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/base64>
or available locally via: info '(coreutils) base64 invocation'
grimwarg-picoctf@webshell:~$ "bDNhcm5fdGgzX3IwcDM1" > file.txt
-bash: bDNhcm5fdGgzX3IwcDM1: command not found
//add the "unknown" text in a file
grimwarg-picoctf@webshell:~$ echo "bDNhcm5fdGgzX3IwcDM1" > file.txt

//run the convertor to decode the file
grimwarg-picoctf@webshell:~$ base64 -d file.txt
l3arn_th3_r0p35
grimwarg-picoctf@webshell:~$ 
//flag is picoCTF{l3arn_th3_r0p35}
