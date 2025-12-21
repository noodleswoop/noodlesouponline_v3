---
tags:
  - ubuntu
  - mpv
---
"[mpv](https://mpv.io/) is a free (as in freedom) media player for the command line. It supports a wide variety of media file formats, audio and video codecs, and subtitle types."

it is also not the most straightforward thing to install on ubuntu!

i am neither smart nor motivated enough to manually update from the github every single time there is an update (though come to think of it i'm not sure the method i used is actually that much different. anyways.). i do however enjoy a bit of a challenge and i've been meaning to mess around with mpv for a while. therefore i went onto the website to see where to start and i was directed [here](https://fruit.je/apt).

however, i am not running debian, and my computer skills are approximately one and a half steps above a box of rocks. so i turned to good old google for answers and found [this post](https://forums.linuxmint.com/viewtopic.php?t=420183). technically it's for mint but mint and ubuntu are similar enough that it really didn't end up mattering.

as always, in case of deletion, i will copypaste the solution here. enter the following commands into the terminal:
```
sudo apt install ffmpeg
sudo curl --output-dir /etc/apt/trusted.gpg.d -O https://apt.fruit.je/fruit.gpg
echo 'deb https://apt.fruit.je/ubuntu jammy mpv'|sudo tee /etc/apt/sources.list.d/fruit.list
sudo apt update && sudo apt install mpv libaacs0
```

(note: you need to install ffmpeg because that's what mpv relies on.) 

if you want to undo what you just did:
```
sudo apt remove mpv ffmpeg sudo rm -v /etc/apt/sources.list.d/fruit.list /etc/apt/trusted.gpg.d/fruit.gpg sudo apt update
```

i have yet to actually attempt to configure mpv, but that's another adventure for another day.