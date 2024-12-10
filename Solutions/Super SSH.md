Super SSH

Description
Using a Secure Shell (SSH) is going to be pretty important. Can you ssh as ctf-player to titan.picoctf.net at port 53529 to get the flag? You'll also need the password 6dd28e9b. If asked, accept the fingerprint with yes. If your device doesn't have a shell, you can use: https://webshell.picoctf.org If you're not sure what a shell is, check out our Primer: https://primer.picoctf.com/#_the_shell

Solution

//get some help for ssh
grimwarg-picoctf@webshell:~$ ssh --help
unknown option -- -
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface]
           [-b bind_address] [-c cipher_spec] [-D [bind_address:]port]
           [-E log_file] [-e escape_char] [-F configfile] [-I pkcs11]
           [-i identity_file] [-J [user@]host[:port]] [-L address]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-Q query_option] [-R address] [-S ctl_path] [-W host:port]
           [-w local_tun[:remote_tun]] destination [command [argument ...]]
grimwarg-picoctf@webshell:~$ 

//use provided username and port
grimwarg-picoctf@webshell:~$ ssh -l ctf-player titan.picoctf.net -p 60618
The authenticity of host '[titan.picoctf.net]:60618 ([3.139.174.234]:60618)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:4: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:60618' (ED25519) to the list of known hosts.

//type the password, it doesn't appear in the shell input field
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.
