---
layout:     post
title:      The Cyber Grabs Ctf writeup
date:       2022-02-7 14:37
summary:    Brain and body is dead after this one
categories: Ctf writeups
---

## Competition details
---
[The Cyber Grabs competition 2022](https://ctftime.org/event/1556)

I played under Th3 Clu3le55 0nes and managed to get 7th place among the 285 teams globally.

## Forensics
---
### Mr Robot
Challenge description:

Mr. Robot most famous TV show but least people know about it.

Flag Format: CYBERGRABS{}

[audio file](/Cybergrabs/chall.wav)

Writeup:
Initially I tried to a lot of forensics method on it including sstv, extracting files from it, stegnography and extracting lsb.
After about 5 hours of trying, I checked with the admin and realised that I missed the flag. So after going through all of the process again, extracting lsb using [lsb stego](https://github.com/ragibson/Steganography) actually gives us a flag... Wasted my time on this ;-;

Flag: CYBERGRABS{3VERY_8YTE_4RE_REAL_VALUE}

## Web
---
### Easy web
Challenge description:

No caption needed...

Flag Format: cybergrabs{}

Writeup:
Very easy web challenge. Since there is nothing on the website itself, 
[Website design](/Cybergrabs/Easyweb1.png)
Theres really nothing on the website, so I went to check for cookies which returns a value
[Cookie value](/Cybergrabs/Easyweb2.png)
Cookie : Y3liZXJncmFic3tpdHNfZWFzeV93ZWJ9
Now going onto [Cyberchef](https://gchq.github.io/CyberChef/) , we can find out that Y3liZXJncmFic3tpdHNfZWFzeV93ZWJ9 is in base 64

Flag: cybergrabs{its_easy_web}

### Rabbit
Challenge description:

Hackers, the task is to boot the machine, and, well, root it.
This is basically just a web challenge, with one flag, flag.txt.

flag format: CyberGrabs{}

[This challenge was hosted on try hack me](https://tryhackme.com/room/thecybergrabs0x03web)

Writeup:
It was so laggy when I tried to solve this challenge but you can just get the flag by adding /flag.txt behind ur machine instance's ip address. 

Flag : CyberGrabs{rabbit_under_rabbit_under_rabbithole_adios}

## Reverse Engineering
---
### aah shit!
Challenge description:

Where are we going?

Flag format: cybergrabs{}

[file](/Cybergrabs/ahh_shit)

Writeup:
Used IDA PRO 64 to disassemble to file and found this line of code.
{% highlight c %}
int __cdecl main(int argc, const char **argv, const char **envp)
{
  char v4[32]; // [rsp+10h] [rbp-90h] BYREF
  char s[104]; // [rsp+30h] [rbp-70h] BYREF
  unsigned __int64 v6; // [rsp+98h] [rbp-8h]

  v6 = __readfsqword(0x28u);
  qmemcpy(v4, "h3r3_w3_g0_4g4in!", 17);
  puts("Serving for a second.... cause that's what I do!!");
  sprintf(s, "echo %s | nc 0.0.0.0 %d", v4, 9999LL);
  system(s);
  return 0;
}
{% endhighlight %}

Flag : cybergrabs{h3r3_w3_g0_4g4in!}

## Osint
---
### Wayback 1
Challenge description:

Some answers are hidden in the past, Whose website theme did we “cyberange.io” used when we first went public.

Flag Format: flag{firstname_lastname}

Writeup:
Wayback suggests wayback machine, so using that we can get the flag.

Flag : flag{Andrea_Galanti}

### Wayback 2
Challenge description:

Some answers are hidden in the past, Find the phone number of the person in Wayback 1

Flag Format: flag{987...5645}

Writeup:
I personally never tried this challenge but im pretty sure it is found on the website on sth.

### Wayback 2
Challenge description:

Some answers are hidden in the past, his number is unavailable now, find his skype id

Flag Format: flag{skypeid}

Writeup:
I also personally never tried this challenge but when I saw the challenge, im pretty sure you have to use [this](https://tools.epieos.com/email.php)

### Hashtag
Challenge description:

Some answers are hidden in the details, Find the hashtag used by the author of this image. [Image](/Cybergrabs/meta_image.jpg)

Flag Format: flag{smallcasetext}

Writeup:
This image has exif data encoded in it which tells you more details about the image. Use [Cyberchef](https://gchq.github.io/CyberChef/) and extract exif, we can find out that the author is xphotographer4. Using this username, go on social media to find if any accounts match. Tried Instagram and then twitter, and boom theres the hashtag.
[twitter account](https://twitter.com/XPhotographer4)

Flag : flag{thisisawesome}

### Hotel
Challenge description:

Some answers are hidden in the details, Find the hotel from where this image was uploaded. [Image](/Cybergrabs/meta_image.jpg)

Flag Format: flag{smallcasetext}

Writeup:
Exif returned no coordinates on cyberchef for some reason but I opened the file in [Hex viewer](https://hexed.it/) and is able to find the geographical location and found the Leonardo Hotel Rembrandtpark, Staalmeesterslaan 410, 1057 PH Amsterdam, Netherlands

Flag : flag{leonardo}

## Miscellaneous
---
### First telecommunication
Challenge description:

Decode the First Telecommunication Code.

10101 11000 00111 11010 11000 10000 10000 10100 00110 00101 11001 00011 00111 01001 11000 10000

Flag Format: cybergrabs{}

Writeup:
I went to [Decode identifier](https://www.dcode.fr/cipher-identifier) and found out about [baudot code](https://www.dcode.fr/baudot-code).

Flag : cybergrabs{YOUGOTTHISBAUDOT}

### Electronics
Challenge description:

Decode it...

+---+++-+- -+--+++-+- -+--+-+++- -+--++-++- ---+++-++- +-++--++-- -+-+--+++- -+-+++--+- -++-+++--- -+--++-++- +-++--+-+- -+-+++--+- +-+-++--+- -+++-+-+-- +++-+---+-

Flag Format: cybergrabs{lowercase}

Writeup:
I went to [Decode identifier](https://www.dcode.fr/cipher-identifier) and found out about [decabit code](https://www.dcode.fr/decabit-code).

Flag : cybergrabs{decabit_was_fun}


There are more challenges I have attempted but Im too lazy to write the writeups...