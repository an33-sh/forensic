FORENSICS
=========

SNOW SNOW
---------

using ```stegsnow``` we can find the encoded flag
then we have to decode it by rotating the letter by rot18

```
$ stegsnow -C av_a0b05a70-7bc0-419e-bc50-147852117b9c.txt


```

10111001
--------

using ```zsteg``` we can get the lsb data , from which we can get the encoded flag
it is base32 encoded, we can decode it to get the flag

```
$ zsteg av_573d13aa-bccd-441f-88f2-0a5fe94e524e.png
```
BACK TO SANANDREAS
------------------

In the challenge hit some letter are give capital which give ```JSTEG``` So we can use jsteg agianst the jpg file to  get a link
and when we go the link we can get the flag
```
$ jsteg reveal av_b7cfaf3c-883f-4818-8da2-0bcd8360fbb8.jpg a.txt
```
flag : inctfj{gr0ve_5treet_f0r_l1fe}

ALWAYS HAS BEEN
---------------
from the challenge discrytion we can get a hint that we change the image to ```BLUE PLANE``` ,Using stegsolve we can change the plane
and get the flag from it

flag:inctfj{th3_fl4g_wa5_liter4lly_ins1de_4_m3me}

JAY-CHOT
---------
In this challenge we are give a ```.jpg``` , but it is not openning
when we check the  in hexedit in the magic bytes instead of ```FF D8 FF E0```   ther ```FF D9 FF E0``` 
we can edit it and open it and get teh flag
flag:flag{a4aa04741a8d3a952a7ec88457991b97}

 MY-FIRST-STENGOGRAPHY
 ---------------------
 In this challenge we have two jpg file,which has soem file inside it we have to find it
 using ```steghide``` we can ddecode it
 
 ```
 steghide extract -sf av_9f437f5f-aa31-4109-b07f-3650c4e31d1d.jpg #with no password
 ```
 we get the pasword for the second file

```
steghide extract -sf av_c02de02d-0f7c-4732-bf60-26acc37470f0.jpg 
```
give the password got from the first got password.txt
then we get a plans.txt with flag inside it

flag:inctfj{w3_4r3_pl4nt1ng_4_b0mb}

YOU CAN'T SEE ME
-----------------
In this we get a png file which cannot be opened,if we check it with hex edit we can see that the **magic bytes** and 
**critical chunks** are corrupted
so we can edit it using ```hexedit``` or ```ghex```
```
IDHR => IHDR
idat => IDAT
INED => IEND
```
after saving the file we can open it and see the flag
flag:inctf{WH4T_ar3_pNgCHUnkS?}
