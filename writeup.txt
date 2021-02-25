Forensics_set_2
===============


Z_challenge3
------------

In this challenge we are given png image "Z_challenge.png"
 when opening the image we can see its a QRCODE so we have decode the flag from 
it
the tool i used was "zbarimg" 
``$ zbarimg "Z_challenge3.png ``
by this we command we can get the flag
 flag:flag{N0w_y0u_a_little_about_zbarimg}





stringer-Things
--------------

In this challenge we are given two files 
1)find-flags-in-me
2)flag.txt

In the flag.txt it says
"""
Obviously, this is not the flag, but I can give you the flag format.

inctf{s0m3_l33t_str1ng}

PS: "inctf" in the flag is also case insensitive. Find three flags in the file.
"""

from the title 
of the challenge we get some idea we have to find some sort of string in the file so I tried ```$strings find-flags-in-me``` then i get lot of ulgy stuff then i grep the flag throug it
```$strings find-flags-in-me | grep inctf``` i greped inctf because it is our flag format thus we get the first flag
 flag1:inctf{y4yy!!!_found_th3_fir5t_fl4g}
 
 next flag w want to use grep -i inctf after strings
 
 flag2:InCtF{G00d_jobb!!This_is_the_2nd_on3}
 
 for third flag i used hexedit and search for inctf ascii
 
 
 	 inctf{th1s_1s_th3_l4st_0ne}

ss_challenge
------------

in this challenge we are given a png file when we open it in normal image viewer there is only three color shapes ,so i opened it in the stegsolve and changed the planes at Redplane 1 we will get the flag
flag:pctf{st3gsolv3_is_us3ful}

E-challenge
-----------

in this challenge we are give a jpeg file ,by using exiftool we can extract the metadata of the image
```exiftool E_challenge3.jpeg 
```
from the comment header we get some hex string by decoding it we can get the flag
flag:inctf{3x1f700L_is_g00d_!_guess_!!!}


b_challenge
-----------

In this we are give a jpg file ,i used binwalk to check that if any files are embede in it
```
$ binwalk -e b_challenge3.jpg 
```
and found there is zip file in it and the then i used dd to exctract the file
```
$ dd if=b_challenge3.jpg of=Free.zip bs=1 skip=202
```
in that zip file there is a image 'Freedom.jpg' ,when we open it we get the flag
flag:inctf{fr33dom_w4s_n0t_w0n_0vernit3}

sh_challenge
------------

in this we are give a jpg file and we  have to find the flag inside it
i used steg hide but it needs a passphrase to extract file so 
i outputed the string inside in the image and i got hex number and they i decode from hex and they i got a base64 string and then i decoded it and get
``FlareInTheHole``
when i used it as password for steg hide we get flag.txt and inside it was the flag
flag:inctf{1_l0ve_c0unt3r_str1ke_1.6}

twins
------

i used cmp to compare two file and printed the differing bytes
```
$ cmp -b -l Twin1 Twin2
```
flag : inctf{y0u_Got_m3}

