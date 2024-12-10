Mod 26

Description
Cryptography can be easy, do you know what ROT13 is? cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_nSkgmDJE}

Solution
//ROT13 is a simple substitution cipher that replaces each letter with the letter 13 places ahead in the alphabet. 
//It’s often used for obfuscation, and decoding ROT13 is the same as encoding it.
//an easy solution is to search for ROT 13 decoder but I will use the tr (translate) command

grimwarg-picoctf@webshell:~$ tr --help
Usage: tr [OPTION]... SET1 [SET2]
Translate, squeeze, and/or delete characters from standard input,
writing to standard output.

  -c, -C, --complement    use the complement of SET1
  -d, --delete            delete characters in SET1, do not translate
  -s, --squeeze-repeats   replace each sequence of a repeated character
                            that is listed in the last specified SET,
                            with a single occurrence of that character
  -t, --truncate-set1     first truncate SET1 to length of SET2
      --help     display this help and exit
      --version  output version information and exit

SETs are specified as strings of characters.  Most represent themselves.
Interpreted sequences are:

  \NNN            character with octal value NNN (1 to 3 octal digits)
  \\              backslash
  \a              audible BEL
  \b              backspace
  \f              form feed
  \n              new line
  \r              return
  \t              horizontal tab
  \v              vertical tab
  CHAR1-CHAR2     all characters from CHAR1 to CHAR2 in ascending order
  [CHAR*]         in SET2, copies of CHAR until length of SET1
  [CHAR*REPEAT]   REPEAT copies of CHAR, REPEAT octal if starting with 0
  [:alnum:]       all letters and digits
  [:alpha:]       all letters
  [:blank:]       all horizontal whitespace
  [:cntrl:]       all control characters
  [:digit:]       all digits
  [:graph:]       all printable characters, not including space
  [:lower:]       all lower case letters
  [:print:]       all printable characters, including space
  [:punct:]       all punctuation characters
  [:space:]       all horizontal or vertical whitespace
  [:upper:]       all upper case letters
  [:xdigit:]      all hexadecimal digits
  [=CHAR=]        all characters which are equivalent to CHAR

Translation occurs if -d is not given and both SET1 and SET2 appear.
-t may be used only when translating.  SET2 is extended to length of
SET1 by repeating its last character as necessary.  Excess characters
of SET2 are ignored.  Only [:lower:] and [:upper:] are guaranteed to
expand in ascending order; used in SET2 while translating, they may
only be used in pairs to specify case conversion.  -s uses the last
specified SET, and occurs after translation or deletion.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/tr>
or available locally via: info '(coreutils) tr invocation'
grimwarg-picoctf@webshell:~$ 

//tr 'A-Za-z' 'N-ZA-Mn-za-m':
//  A-Za-z: Matches all uppercase and lowercase letters.
//  N-ZA-Mn-za-m: Translates each letter by shifting 13 places forward (ROT13).
grimwarg-picoctf@webshell:~$ echo "cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_nSkgmDJE}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
picoCTF{next_time_I'll_try_2_rounds_of_rot13_aFxtzQWR}
grimwarg-picoctf@webshell:~$ 
