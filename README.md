# Can not record audio with kazam in Ubuntu 20.04 #

## Detail ##
OS : Ubuntu 20.04 <br />
kazam version : kazam 1.4.5

## Solution ##

### 1. make sure installed include package ###

``` sudo apt install python3-cairo python3-xlib ```

#### python3-cairo ####
Cairo is a library for drawing vector graphics. Vector graphics are interesting because they don’t lose clarity when resized or transformed.
Pycairo is a set of bindings for cairo. It provides the cairo module which can be used to call cairo commands from Python.

#### python3-xlib ####
The Python X Library is intended to be a fully functional X client library for Python programs. It is written entirely in Python, in contrast 
to earlier X libraries for Python (the ancient X extension and the newer plxlib) which were interfaces to the C Xlib

### 2. change a lib of kazam ###
backup older file, **always backup your older source code, and you can change default again**

```sudo mv pulseaudio.py pulseaudio.py.backup``` <br />

download raw in this repo or you can copy source code in [pulseaudio.py](https://raw.githubusercontent.com/Kyuubang/kazam-pulseaudio-issue/master/pulseaaudio.py)

##### Download #####

```shell
curl -L -o /usr/lib/python3/dist-packages/kazam/pulseaudio/pulseaudio.py https://raw.githubusercontent.com/Kyuubang/kazam-pulseaudio-issue/master/pulseaaudio.py
```

##### Copy #####

```sudo gedit /usr/lib/python3/dist-packages/kazam/pulseaudio/pulseaudio.py``` copy,paste,and save

### Close your kazam and open again ###
Enjoy!! :+1: :sparkles:

## Reference ##
https://github.com/hzbd/kazam/blob/master/kazam/pulseaudio/pulseaudio.py <br />
https://askubuntu.com/questions/1234314/screen-recording-applications-are-not-detecting-audio-in-ubuntu-20-04?fbclid=IwAR2RQQCCskrxoR01LhSTc6RElujBcPIAi_ZvP5O8EQarJmveGKK0Ba7uaHY<br />
http://onnocenter.or.id/wiki/index.php/Kazam:_audio_di_Ubuntu_20.04
