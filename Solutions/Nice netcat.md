Nice netcat...

Description
There is a nice program that you can talk to by using this command in a shell: $ nc mercury.picoctf.net 22342, but it doesn't speak English...

Solution
//run command to get the ascii flag
grimwarg-picoctf@webshell:~$ nc mercury.picoctf.net 22342
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
53 
102 
98 
53 
101 
53 
49 
100 
125 
10 

//use an ascii to text converter (https://www.duplichecker.com/ascii-to-text.php) to "translate the flag"
flag is picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}