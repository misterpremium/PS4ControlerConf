# PS4ControllerConf
Configuration to use ps4 controller with xboxdrv

To work properly with steam, in the game properties, we have to set the option "Override for..." to "Disable Steam Input"

![image](https://user-images.githubusercontent.com/25362037/111073732-0ec0f700-84e0-11eb-8952-fc65000e1f78.png)

Then, we have to install xboxdrv and evtest, in order to configure the controller.

To find the event numbre of the controller we have to run evtest:
```
$ evtest 
No device specified, trying to scan all of /dev/input/event*
Not running as root, no devices may be available.
Available devices:
/dev/input/event31:     Wireless Controller
```

With that information we can edit the confing file.

Then we can launch the xboxdrv
```
$ sudo xboxdrv --config /pathTo/ps4.xboxdrv --mimic-xpad-wireless
xboxdrv 0.8.8 - http://pingus.seul.org/~grumbel/xboxdrv/ 
Copyright © 2008-2011 Ingo Ruhnke <grumbel@gmail.com> 
Licensed under GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html> 
This program comes with ABSOLUTELY NO WARRANTY. 
This is free software, and you are welcome to redistribute it under certain conditions; see the file COPYING for details. 


Your Xbox/Xbox360 controller should now be available as:
  /dev/input/js2
  /dev/input/event21

Press Ctrl-C to quit, use '--silent' to suppress the event output
X1:     0 Y1:  -768  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0
X1:  -512 Y1:  -768  X2:     0 Y2:     0  du:0 dd:0 dl:0 dr:0  back:0 guide:0 start:0  TL:0 TR:0  A:0 B:0 X:0 Y:0  LB:0 RB:0  LT:  0 RT:  0

```

With the option --silent we can hide the stdout of the command.
