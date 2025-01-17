---
title: "Music Generator"
date: 2019-01-24
permalink: /posts/2019/01/Music-Generator
excerpt: 'Implementation of DCGAN music generating software using it’s image format - piano roll. It’s a part of my diploma thesis. I’ve presented its results on ICAISC 2019 in Zakopane.'
tags:

  - DCGAN
  - Music Generation
  - Python
---
**UPDATE 11.19** - Preprint available ["Application of Deep Neural Networks to Music Composition Based on MIDI Datasets and Graphical Representation"](https://www.mateuszdorobek.pl/files/ICAISC2019_musicGAN_preprint.pdf)

**UPDATE 07.19** - New article ["Use of artificial intelligence for generating musical contents"](https://github.com/mateuszdorobek/Music-Generator/blob/master/Article.pdf) PL. 

Music at [SoundCloud](https://soundcloud.com/mateuszdorobek/sets/ai-music), Code on [GitHub](https://github.com/mateuszdorobek/Music-Generator)

<iframe width="100%" height="450" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/719803656&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>
# Input Data

I've decided to use piano roll format, because it has less data redundancy than wave form and spectrogram:

<img src="https://raw.githubusercontent.com/mateuszdorobek/Music-Generator/master/images/music_formats_%20comparition.png" width="800" align="middle" title="Music Formats Comparition">

Images in piano roll format was created from two midi databases:

| Name                                                         | Description                                 | Data type   | Data size          |
| ------------------------------------------------------------ | ------------------------------------------- | ----------- | ------------------ |
| [Dough McKeznie](https://bushgrafts.com/midi/)               | Jazz Piano Solo                             | MIDI        | ~300 pieces, 20h   |
| [MAESTRO](https://magenta.tensorflow.org/datasets/maestro#dataset) | Recordings from classical piano competition | Wave & MIDI | ~2500 pieces, 170h |

Using scripts in [MidiScripts](https://github.com/mateuszdorobek/Music-Generator/tree/master/MidiScripts) I've transformed raw midi files into piano roll image format. 


#### Preprocessing steps:

- Removing unnecessary markers from MIDI file using [mtxClearScript.py](https://github.com/mateuszdorobek/Music-Generator/blob/master/MidiScripts/mtxClearScript.py)
- Quantizing midi events to 30ms using [mtxQuantizeScript.py](https://github.com/mateuszdorobek/Music-Generator/blob/master/MidiScripts/mtxQuantizeScript.py)
- Merging all midi files with [mtxMergeScript.py](https://github.com/mateuszdorobek/Music-Generator/blob/master/MidiScripts/mtxMergeScript.py) into one big pixel matrix 
- Dividing and converting with [mtxCompressScript.py](https://github.com/mateuszdorobek/Music-Generator/blob/master/MidiScripts/mtxCompressScript.py) into training image set.

#### Sample MIDI in text format (MIDI is basically binary file)
```
MFile 1 2 384
MTrk
0 Tempo 500000
0 TimeSig 4/4 24 8
1 Meta TrkEnd
TrkEnd
MTrk
0 PrCh ch=1 p=0
806 On ch=1 n=42 v=71
909 Par ch=1 c=64 v=37
924 Par ch=1 c=64 v=50
939 Par ch=1 c=64 v=58
955 Par ch=1 c=64 v=62
970 Par ch=1 c=64 v=65
986 Par ch=1 c=64 v=68
...
```
### Piano Roll example:
<img src="https://raw.githubusercontent.com/mateuszdorobek/Music-Generator/master/images/img.png?token=AQ9tTYisSGQLtBd-wC1vXO8bEgenRsebks5cgXUcwA%3D%3D" width="400" align="middle" title="Input Image">

# Neural Network
I've decided to use DCGAN architecture described and implemented [here](https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html) 
#### Structure of DCGAN:
<img src="https://camo.qiitausercontent.com/d20575271ed262c2d75d8deed30f1f84809be141/68747470733a2f2f71696974612d696d6167652d73746f72652e73332e616d617a6f6e6177732e636f6d2f302f36343333342f64336566623363342d386130632d653438642d373239382d3538303834393461326266342e706e67"  width="500" title="DCGAN Structure">

# Training
To train I've used [Google Collaboratory](colab.research.google.com) with their amazing **Tesla K80**, and my private device with **NVidia 1050Ti** which performed really well.
As a result of training I've received bunch of indistinguishable images which I've to transform back to midi form with [imagesDecodeScript.py](https://github.com/mateuszdorobek/Music-Generator/blob/master/MidiScripts/imagesDecodeScript.py)

![Fake vs Real](https://raw.githubusercontent.com/mateuszdorobek/Music-Generator/master/images/Fake%20vs%20Real.png?token=AQ9tTS3Gwu_EG1oyGgVLGJGHY8E0xcTHks5cgXvbwA%3D%3D)

Overall cost function in first experiments seems to prove some overfitting, but in this kind of images it's nothing surprising.

![Cost Function](https://raw.githubusercontent.com/mateuszdorobek/Music-Generator/master/images/G%26D%20Loss.png?token=AQ9tTWjsbX7O7GxkGVsMZuVQeG2GQYMWks5cgXxcwA%3D%3D)

And here we have one of the most beautiful things in using GAN networks, learning progress animation


![GIF](https://github.com/mateuszdorobek/Music-Generator/blob/master/images/gif_short.gif?raw=true)

# Results

As always not the theory, but results are the most interesting thigs in this type of projects. 

Look at [examples](https://github.com/mateuszdorobek/Music-Generator/tree/master/music) where you can find music generated using DCGAN. 

# Tech Stack

<img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"  height="60" title="Github"><img src="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/12/PyTorch-logo.jpg"  height="60"  title="Github"><img src="https://www.fullstackpython.com/img/logos/pycharm.jpg"  height="60" title="Pycharm Logo"><img src="https://upload.wikimedia.org/wikipedia/en/c/cd/Anaconda_Logo.png"  height="60" title="Anaconda Logo">



24 Jan 2019 - [Mateusz Dorobek](https://mateuszdorobek.pl)