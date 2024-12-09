strings it

Description
Can you find the flag in file without running it?

Solution
//download the file
grimwarg-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
--2024-12-09 13:36:52--  https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                                             100%[=================================================================================================================================================================>] 757.84K  1.86MB/s    in 0.4s    

2024-12-09 13:36:53 (1.86 MB/s) - 'strings' saved [776032/776032]

grimwarg-picoctf@webshell:~$ ls
README.txt  strings
//get some help about strings function
grimwarg-picoctf@webshell:~$ strings --help
Usage: strings [option(s)] [file(s)]
 Display printable strings in [file(s)] (stdin by default)
 The options are:
  -a - --all                Scan the entire file, not just the data section [default]
  -d --data                 Only scan the data sections in the file
  -f --print-file-name      Print the name of the file before each string
  -n <number>               Locate & print any sequence of at least <number>
    --bytes=<number>         displayable characters.  (The default is 4).
  -t --radix={o,d,x}        Print the location of the string in base 8, 10 or 16
  -w --include-all-whitespace Include all whitespace as valid string characters
  -o                        An alias for --radix=o
  -T --target=<BFDNAME>     Specify the binary file format
  -e --encoding={s,S,b,l,B,L} Select character size and endianness:
                            s = 7-bit, S = 8-bit, {b,l} = 16-bit, {B,L} = 32-bit
  --unicode={default|show|invalid|hex|escape|highlight}
  -U {d|s|i|x|e|h}          Specify how to treat UTF-8 encoded unicode characters
  -s --output-separator=<string> String used to separate strings in output.
  @<file>                   Read options from <file>
  -h --help                 Display this information
  -v -V --version           Print the program's version number
strings: supported targets: elf64-x86-64 elf32-i386 elf32-iamcu elf32-x86-64 pei-i386 pe-x86-64 pei-x86-64 elf64-l1om elf64-k1om elf64-little elf64-big elf32-little elf32-big pe-bigobj-x86-64 pe-i386 srec symbolsrec verilog tekhex binary ihex plugin
Report bugs to <https://sourceware.org/bugzilla/>

//use strings and grep functions in one line to get the flag
grimwarg-picoctf@webshell:~$ strings strings | grep 'picoCTF'
picoCTF{5tRIng5_1T_d66c7bb7}
grimwarg-picoctf@webshell:~$ 

//we can also redirect the output to a text file and search in it 
grimwarg-picoctf@webshell:~$ strings strings > file.txt

//we can see that the file size on disk is quite big
grimwarg-picoctf@webshell:~$ ls -lh file.txt 
-rw-rw-r-- 1 grimwarg-picoctf grimwarg-picoctf 381K Dec  9 13:38 file.txt
grimwarg-picoctf@webshell:~$ du -h  file.txt 
384K    file.txt
grimwarg-picoctf@webshell:~$ 
