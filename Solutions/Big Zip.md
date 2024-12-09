Big Zip

Description
Unzip this archive and find the flag.
Download zip file

Solution
grimwarg-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/503/big-zip-files.zip
--2024-12-09 13:02:12--  https://artifacts.picoctf.net/c/503/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: 'big-zip-files.zip'

big-zip-files.zip                                                   100%[=================================================================================================================================================================>]   3.04M  1.82MB/s    in 1.7s    

2024-12-09 13:02:14 (1.82 MB/s) - 'big-zip-files.zip' saved [3182988/3182988]

grimwarg-picoctf@webshell:~$ ls
README.txt  big-zip-files.zip
grimwarg-picoctf@webshell:~$ unzip big-zip-files.zip 

 inflating: big-zip-files/folder_tdhydyuvdy/folder_ojukuxercg/folder_eottozrqne/folder_nddocpydlm/file_bwhpfggkbvywzh.txt  
  inflating: big-zip-files/folder_tdhydyuvdy/folder_ojukuxercg/folder_eottozrqne/folder_nddocpydlm/qmhwhcdz.txt  
  inflating: big-zip-files/folder_tdhydyuvdy/folder_ojukuxercg/folder_eottozrqne/folder_nddocpydlm/crulvejtqsczbpbglxacm.txt  
  //a lot of files 
  ...
  //a lot of files 
  inflating: big-zip-files/folder_wdhgdgrbfc/gnsnwwhmlslslscapr.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/file_ximyquuowm.txt  
  inflating: big-zip-files/folder_wdhgdgrbfc/siizcxeduftjnvian.txt  
  inflating: big-zip-files/mktyhgmedcj.txt  

//after reading grep help I saw that I can search recursive for patern in a folder
grimwarg-picoctf@webshell:~$ grep 'picoCTF' -r big-zip-files
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
