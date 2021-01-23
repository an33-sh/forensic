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
