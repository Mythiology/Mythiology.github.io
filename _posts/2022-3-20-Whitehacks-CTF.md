---
layout:     post
title:      Whitehacks CTF writeup
date:       2022-03-20
summary:    Anxiety at its finest
categories: Ctf writeups
---

## Competition details
[Whitehacks competition 2022](https://whitehacks.scis.smu.edu.sg/)

I played under RVCTF TH3 CLU3LE55 0NES and managed to get 1st place among the 130 teams locally.

---
## MISCELLANEOUS

### Sanity check
Challenge description:

Welcome to Whitehacks 2022! As a sanity check, please proceed to our official Discord server and find the flag!
Join our Discord Server [here](https://discord.gg/eUAhxhSZdH)

Writeup:
After playing in ctf.sg and experiencing the sanity category, this meme represents how this challenge was to me...

             No Sanity?
⠀⣞⢽⢪⢣⢣⢣⢫⡺⡵⣝⡮⣗⢷⢽⢽⢽⣮⡷⡽⣜⣜⢮⢺⣜⢷⢽⢝⡽⣝
⠸⡸⠜⠕⠕⠁⢁⢇⢏⢽⢺⣪⡳⡝⣎⣏⢯⢞⡿⣟⣷⣳⢯⡷⣽⢽⢯⣳⣫⠇
⠀⠀⢀⢀⢄⢬⢪⡪⡎⣆⡈⠚⠜⠕⠇⠗⠝⢕⢯⢫⣞⣯⣿⣻⡽⣏⢗⣗⠏⠀
⠀⠪⡪⡪⣪⢪⢺⢸⢢⢓⢆⢤⢀⠀⠀⠀⠀⠈⢊⢞⡾⣿⡯⣏⢮⠷⠁⠀⠀
⠀⠀⠀⠈⠊⠆⡃⠕⢕⢇⢇⢇⢇⢇⢏⢎⢎⢆⢄⠀⢑⣽⣿⢝⠲⠉⠀⠀⠀⠀
⠀⠀⠀⠀⠀⡿⠂⠠⠀⡇⢇⠕⢈⣀⠀⠁⠡⠣⡣⡫⣂⣿⠯⢪⠰⠂⠀⠀⠀⠀
⠀⠀⠀⠀⡦⡙⡂⢀⢤⢣⠣⡈⣾⡃⠠⠄⠀⡄⢱⣌⣶⢏⢊⠂⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⢝⡲⣜⡮⡏⢎⢌⢂⠙⠢⠐⢀⢘⢵⣽⣿⡿⠁⠁⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠨⣺⡺⡕⡕⡱⡑⡆⡕⡅⡕⡜⡼⢽⡻⠏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⣼⣳⣫⣾⣵⣗⡵⡱⡡⢣⢑⢕⢜⢕⡝⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⣴⣿⣾⣿⣿⣿⡿⡽⡑⢌⠪⡢⡣⣣⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⡟⡾⣿⢿⢿⢵⣽⣾⣼⣘⢸⢸⣞⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠁⠇⠡⠩⡫⢿⣝⡻⡮⣒⢽⠋⠀⠀

If im going to be honest, this is the hardest challenge of whitehacks so far (no cap).

So from the challenge description, we are told to go to their discord server and find the flag. Make sure to check through every single text channel and the history to see if the flag has been posted there. If you look for it hard enough, you will find it in the description of the channel #flag

To be entirely honest, you can actually find the flag before the ctf even started through discord plugins on chrome that allows u to see hidden vc and hidden text channels even though you do not have the permissions.

Flag: WH2022{w3lc0m3_t0_wh2022}
---


---
## OSINT

### The War of The Worlds 2 - Humans or ET?
Difficulty: Medium
Challenge description:

Hmm, I think it may be worth taking a deeper look at this Kurt person. See if they have something to do with Lewis' disappearance. Be careful though, make sure that he doesn't know that you are investigating him.

Maybe this "Ng Eng Siang Kurt" has a social media or something?

Writeup:
So the challenge description asked us to find `Ng Eng Siang Kurt` social media. Initially, I thought that I will only find him on a professional / work related website since the previous challenges stated that he has started an organisation. After failing to find him on Linkedin and Facebook, I went onto instagram as my last hope and I found this account. 

[(ngengsiangkurt)](https://www.instagram.com/ngengsiangkurt/?hl=en)

So just buy taking a look at his posts, we can already tell that there is something suspicious on his first post where it shows the straits times but the url does not reflect the same. Another thing that was suspicious was the account `not_alien_123` but lets take one step at a time first.

[(Suspicious url)](https://shorturl.at/krA04)

Going to the suspicious url, we get the left side of the qr code which means that we still need to find the second half of the qr code. 

Whenever we do this osint challenges, if we meet a deadend we need to retrace our steps and think about what else is suspicious. So lets now take a look at `not_alien_123` account.

[(not_alien_123)](https://www.instagram.com/not_alien_123/?hl=en)

`A reasonable human being. Find me on TikTok!` Following this lead, we are able to his tiktok account and his one post.

[(Sus post (Is that an amongus reference?))](https://www.tiktok.com/@not_alien_123/video/7066686049732398338?is_copy_url=1&is_from_webapp=v1)

Halfway about the video there will be a short qr code being flashed which is exactly what we needed to complete our qr code. Using powerpoint presentation (i was lazy okay...), we can arrange the two halves of the qr code into one to which we can scan using our phone and get this link.

[(Qr code link)](https://pastebin.com/WW190H2W)

But it is password protected, this took me a while but I retraced my steps and remembered that `ngengsiangkurt` mentioned that the meaning of life is forty-two... This was kind of a cruel joke but I was just happy that I found the password before the end of the ctf.

Reading through the pastebin, theres nothing suspicious except for the classified section.


===== START OF CLASSIFIED SECTION =====

56 47 68 6c 49 47 68 31 62 57 46 75 49 47 46 77 63 47 56 68 63 6e 4d 67 64 47 
38 67 59 6d 55 67 62 6d 46 74 5a 57 51 67 54 47 56 33 61 58 4d 73 49 48 4e 30 
64 57 52 35 61 57 35 6e 49 47 46 30 49 47 45 67 62 47 39 6a 59 57 77 67 64 57 
35 70 64 6d 56 79 63 32 6c 30 65 53 42 6f 5a 58 4a 6c 4c 67 6f 4b 53 47 55 67 
59 6d 56 73 61 57 56 32 5a 53 42 30 61 47 46 30 49 43 4a 68 62 47 6c 6c 62 69 
49 67 5a 58 68 70 63 33 52 7a 4c 43 42 68 62 6d 51 67 62 57 46 35 49 47 68 68 
64 6d 55 67 59 57 78 6c 63 6e 52 6c 5a 43 42 6f 61 58 4d 67 5a 6e 4a 70 5a 57 
35 6b 63 79 42 68 59 6d 39 31 64 43 42 31 63 79 34 4b 43 6c 64 70 62 47 77 67 
62 6d 56 6c 5a 43 42 74 62 33 4a 6c 49 47 39 77 5a 58 4a 68 64 47 39 79 63 79 
42 7a 5a 57 35 6b 49 48 52 76 49 48 42 79 62 33 5a 70 5a 47 55 67 5a 47 56 6d 
5a 57 35 7a 5a 53 42 33 61 58 52 6f 49 48 4a 6c 5a 33 56 73 59 58 49 67 49 6e 
4a 76 64 47 46 30 61 57 39 75 49 69 34 4b 43 6b 46 7a 49 47 46 73 64 32 46 35 
63 79 77 67 4e 44 63 67 59 57 35 6b 49 45 74 49 5a 47 68 59 4d 6b 5a 6f 56 45 
56 56 4e 56 6c 71 51 6d 74 52 56 30 30 77 57 57 78 4e 64 30 30 79 53 6b 5a 54 
52 30 70 70 55 48 70 43 52 6b 39 58 53 58 64 56 4d 46 5a 71 55 54 41 30 50 53 
34 3d

===== END OF CLASSIFIED SECTION =====


Chucking this into cyberchef and using the from hex feature. We get this...

VGhlIGh1bWFuIGFwcGVhcnMgdG8gYmUgbmFtZWQgTGV3aXMsIHN0dWR5aW5nIGF0IGEgbG9jYWwgdW5pdmVyc2l0eSBoZXJlLgoKSGUgYmVsaWV2ZSB0aGF0ICJhbGllbiIgZXhpc3RzLCBhbmQgbWF5IGhhdmUgYWxlcnRlZCBoaXMgZnJpZW5kcyBhYm91dCB1cy4KCldpbGwgbmVlZCBtb3JlIG9wZXJhdG9ycyBzZW5kIHRvIHByb3ZpZGUgZGVmZW5zZSB3aXRoIHJlZ3VsYXIgInJvdGF0aW9uIi4KCkFzIGFsd2F5cywgNDcgYW5kIEtIZGhYMkZoVEVVNVlqQmtRV00wWWxNd00ySkZTR0ppUHpCRk9XSXdVMFZqUTA0PS4=

Chucking it in again and using from base 64 this time. we get this message

`
The human appears to be named Lewis, studying at a local university here.

He believe that "alien" exists, and may have alerted his friends about us.

Will need more operators send to provide defense with regular "rotation".

As always, 47 and KHdhX2FhTEU5YjBkQWM0YlMwM2JFSGJiPzBFOWIwU0VjQ04=.
`

So I had no idea what this was so back into cyberchef it goes and cyberchef managed to detect a hint of base64. 

`(wa_aaLE9b0dAc4bS03bEHbb?0E9b0SEcCN`

Using the base64 code and since 47 could only means rot47, we managed to get the flag.

Overall this challenge was quite fun although the author could hv played an even cruel joke by changing the rot47 to 42 and not mention about 47 and the encoded text... But oh well, it was a fun challenge regardless!

Flag: WH2022{th3_5p4c3$_b3tw33n_th3_$t4r}

---

There are more challenges I have attempted but Im too lazy to write the writeups...