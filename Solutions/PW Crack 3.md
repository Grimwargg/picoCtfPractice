PW Crack 3

Description
Can you crack the password to get the flag? Download the password checker [from here](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.py) and you'll need the encrypted [flag](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.flag.txt.enc) and the [hash](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.hash.bin) in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

Solution
// Open level3.py and find all the posible passwords
// open the hash file using "bvi level3.hash.bin" in the web terminal
// there you can see the hash for the correct password
// find a tool that can create md5 hashes and feed it the passwords until the generated hash is equal to the one in the file
// the flag is academy{m45h_fl1ng1ng_f684152a}
