PW Crack 4

Description
Can you crack the password to get the flag? Download the password checker [here](https://challenge-files.cylabacademy.net/library/3e720cabf0fd8ff2c70991623d0a333b45c8ca0caf440841d81d09690115d5bc/level4.py) and you'll need the [encrypted flag](https://challenge-files.cylabacademy.net/library/3e720cabf0fd8ff2c70991623d0a333b45c8ca0caf440841d81d09690115d5bc/level4.flag.txt.enc) and the [hash](https://challenge-files.cylabacademy.net/library/3e720cabf0fd8ff2c70991623d0a333b45c8ca0caf440841d81d09690115d5bc/level4.hash.bin)
in the same directory too.

There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.

Solution
// Open level4.py and find all the posible passwords
// open the hash file using "bvi level3.hash.bin" in the web terminal
// there you can see the hash for the correct password
// create a for loop in terminal that will have as input the hash and all passwords


grimwarg-academy@webshell:~$ python3 -c '
> import hashlib
> target = "96cd09166e990a24052d674a53643d2f"
> arr = ["6288", "6152", "4c7a", "b722", "9a6e", "6717", "4389", "1a28", "37ac", "de4f", "eb28", "351b", "3d58", "948b", "231b", "973a", "a087", "384a", "6d3c", "9065", "725c", "fd60", "4d4f", "6a60", "7213", "93e6", "8c54", "537d", "a1da", "c718", "9de8", "ebe3", "f1c5", "a0bf", "ccab", "4938", "8f97", "3327", "8029", "41f2", "a04f", "c7f9", "b453", "90a5", "25dc", "26b0", "cb42", "de89", "2451", "1dd3", "7f2c", "8919", "f3a9", "b88f", "eaa8", "776a", "6236", "98f5", "492b", "507d", "18e8", "cfb5", "76fd", "6017", "30de", "bbae", "354e", "4013", "3153", "e9cc", "cba9", "25ea", "c06c", "a166", "faf1", "2264", "2179", "cf30", "4b47", "3446", "b213", "88a3", "6253", "db88", "c38c", "a48c", "3e4f", "7208", "9dcb", "fc77", "e2cf", "8552", "f6f8", "7079", "42ef", "391e", "8a6d", "2154", "d964", "49ec"]
> 
> for s in arr:
>     if hashlib.md5(s.encode("utf-8")).hexdigest() == target:
>         print(f"Found element: {s}")
> '
Found element: 507d
grimwarg-academy@webshell:~$ python level4.py 
Please enter correct password for flag: 507d
Welcome back... your flag, user:
academy{fl45h_5pr1ng1ng_f8cf5d9c}
grimwarg-academy@webshell:~$ 

//flag is academy{fl45h_5pr1ng1ng_f8cf5d9c}
