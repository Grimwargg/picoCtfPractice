Tab, Tab, Attack

Description
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip

Solution
//download the zip file
grimwarg-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
--2024-12-09 11:00:11--  https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4521 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                                                100%[=================================================================================================================================================================>]   4.42K  --.-KB/s    in 0s      

2024-12-09 11:00:11 (1.85 GB/s) - 'Addadshashanammu.zip' saved [4521/4521]

//just checking to see it in directory
grimwarg-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt

//read unzip help 
grimwarg-picoctf@webshell:~$ unzip --help 
UnZip 6.00 of 20 April 2009, by Debian. Original by Info-ZIP.

Usage: unzip [-Z] [-opts[modifiers]] file[.zip] [list] [-x xlist] [-d exdir]
  Default action is to extract files in list, except those in xlist, to exdir;
  file[.zip] may be a wildcard.  -Z => ZipInfo mode ("unzip -Z" for usage).

  -p  extract files to pipe, no messages     -l  list files (short format)
  -f  freshen existing files, create none    -t  test compressed archive data
  -u  update files, create if necessary      -z  display archive comment only
  -v  list verbosely/show version info       -T  timestamp archive to latest
  -x  exclude files that follow (in xlist)   -d  extract files into exdir
modifiers:
  -n  never overwrite existing files         -q  quiet mode (-qq => quieter)
  -o  overwrite files WITHOUT prompting      -a  auto-convert any text files
  -j  junk paths (do not make directories)   -aa treat ALL files as text
  -U  use escapes for all non-ASCII Unicode  -UU ignore any Unicode fields
  -C  match filenames case-insensitively     -L  make (some) names lowercase
  -X  restore UID/GID info                   -V  retain VMS version numbers
  -K  keep setuid/setgid/tacky permissions   -M  pipe through "more" pager
  -O CHARSET  specify a character encoding for DOS, Windows and OS/2 archives
  -I CHARSET  specify a character encoding for UNIX and other archives

See "unzip -hh" or unzip.txt for more help.  Examples:
  unzip data1 -x joe   => extract all files except joe from zipfile data1.zip
  unzip -p foo | more  => send contents of foo.zip via pipe into program more
  unzip -fo foo ReadMe => quietly replace existing ReadMe if archive file newer

//unzip in different directoy
grimwarg-picoctf@webshell:~$ unzip Addadshashanammu.zip -d arhivamea
Archive:  Addadshashanammu.zip
   creating: arhivamea/Addadshashanammu/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  

//start navigation inside the obtained hierarchy
grimwarg-picoctf@webshell:~$ cd arhivamea/
grimwarg-picoctf@webshell:~/arhivamea$ cd Addadshashanammu/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu$ cd Almurbalarammi/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ cd Assurnabitashpi/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ cd Maelkashishi/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis$ cd Ularradallaku/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls 
fang-of-haynekhtnamet
//reaching bottom dir. --> run the program to obtain the flag
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 

//faster alternative, you can go directly to the deepest placed folder (using Tab multiple times) and then you can run the program
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ cd ~
grimwarg-picoctf@webshell:~$ ls 
Addadshashanammu.zip  README.txt  arhivamea
grimwarg-picoctf@webshell:~$ cd arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls 
fang-of-haynekhtnamet
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
grimwarg-picoctf@webshell:~/arhivamea/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 