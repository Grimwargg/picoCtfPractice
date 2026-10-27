PW Crack 2

Description
Can you crack the password to get the flag? Download the password checker from [here](https://challenge-files.cylabacademy.net/library/227623e9501e3a811cdf5b1c7a2079f75b2e9ab243364a38830e0a4a2943ce2e/level2.py) and you'll need [the encrypted flag](https://challenge-files.cylabacademy.net/library/227623e9501e3a811cdf5b1c7a2079f75b2e9ab243364a38830e0a4a2943ce2e/level2.flag.txt.enc) in the same directory too

Solution

User@DESKTOP-IMHLGII MINGW64 ~/Downloads
$ python level2.py
Please enter correct password for flag: Traceback (most recent call last):
  File "C:\Users\User\Downloads\level2.py", line 27, in <module>
    level_2_pw_check()
    ~~~~~~~~~~~~~~~~^^
  File "C:\Users\User\Downloads\level2.py", line 17, in level_2_pw_check
    user_pw = input("Please enter correct password for flag: ")
KeyboardInterrupt


User@DESKTOP-IMHLGII MINGW64 ~/Downloads
$ python level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
academy{tr45h_51ng1ng_d99a9ef4}

//I opened the level2.py and checked line 18 and used an ascii to text converter (https://www.duplichecker.com/ascii-to-text.php) to get the password
flag is academy{tr45h_51ng1ng_d99a9ef4}