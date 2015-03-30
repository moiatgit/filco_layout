List of TODO

The list of things to be done in order to configure properly the new
Filco keyboard

- check http://rlog.rgtti.com/2014/05/01/how-to-modify-a-keyboard-layout-in-linux/

- check if possible adding a new layout (ca) without changing jp

  no way

- save original layouts from /usr/share/X11/xkb/symbols/

  ok

- get the map for the key numbers in the filco's layout

  ok

- add the following keys

  ok

  * dead keys for accents open and close, and dieresis

  * enye and ce trencada

  * ordinals ro and ra

  * open exclamation

- document it to allow reproduction on laptop

  - include references to http://www.charvolant.org/~doug/xkb/html/xkb.html

- it should be possible to work properly on the standard 105 keys too.


- some keys are underused. You might want to assign them frequent keys
  that require some combination (e.g. accented letters)

  AE10: just maps to 0 and ~
  The same for AE11-13


Another source
--------------

There's another source of information at: https://wiki.debian.org/Keyboard

Some information obtained from here:

- change keyboard settings with

# dpkg-reconfigure console-data
# dpkg-reconfigure keyboard-configuration
# service keyboard-setup restart

- if restarting service is not enough, you can restart kernel with

# udevadm trigger --subsystem-match=input --action=change

- the keyboard configuration file is etc/default/keyboard

- you can change current keyboard with

$ setxkbmap -rules evdev -model evdev -layout us -variant altgr-intl

Another source
--------------

There's another source at https://www.linux.com/learn/tutorials/769644-hacking-your-linux-keyboard-with-xkb


Curiously enougt you have to unplug/replug the keyboard to make the
changes have effect!


To remap special keys around spacebar you can use something like the
following:

$ xmodmap -e "keycode 102=Prior"

En aquest cas, la comanda assigna pàgina enrere a la tecla
immediata a la dreta de l'espai

