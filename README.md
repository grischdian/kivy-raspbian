# kivy-raspbian

Installing Kivy on Raspberry with Raspbian is a bit tricky. There are some good 
instructions found online but non of them worked completely. Especially if you have
a Raspberry Pi 3B+ and the RaspiLCD combined. 

## Install Kivy on Raspbian 9.8 (latest updates)

Follow the instructions [here](https://kivy.org/doc/stable/installation/installation-rpi.html#manual-installation-on-raspbian-jessie-stretch) on `kivy.org` to install kivy on Raspbian (Jessie/Stretch)

Just use Step 1 - 3 (This will work but take a bit)

Be aware that you might have to use `pip3` instead of `pip` if you have python 2.7 already installed. To check that run `pip --version` to see to which folder pip will install the packages.

Maybe considering using not the Master branch, there is also a branch called `stable-1.10` if you want to go on a more stable version.

## Add at the beginning of your `main.py` the following

```
import os
os.environ['KIVY_GL_BACKEND'] = 'gl'
import kivy
```

## Edit kivy Config located in `~/.kivy/config.ini`
```
[input]
mouse = mouse
device_%(name)s = probesysfs,provider=mtdev
mtdev_%(name)s = probesysfs,provider=mtdev
hid_%(name)s = probesysfs,provider=hidinput
```
## Test it!

Clone the Kivy Git Repo [here](https://github.com/kivy/kivy), go to `./kivy/examples/demo/touchtracer/` and edit the `main.py` according to the instructions above. 

Run with `python3 main.py`

## Support / Contact

Just open an issue ;)
